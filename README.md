<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منظومة الساحل للمواد الغذائية</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <script src="https://unpkg.com/html5-qrcode"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Tajawal', sans-serif; background-color: #f3f4f6; }
        .hidden { display: none; }
        @media print {
            .no-print { display: none !important; }
            .print-only { display: block !important; }
        }
        .print-only { display: none; }
    </style>
</head>
<body class="min-h-screen">

    <!-- Login Section -->
    <div id="login-screen" class="flex items-center justify-center h-screen">
        <div class="bg-white p-8 rounded-xl shadow-lg w-full max-w-md">
            <h1 class="text-2xl font-bold text-center mb-6 text-blue-600">محل الساحل للمواد الغذائية</h1>
            <div class="space-y-4">
                <div>
                    <label class="block mb-1">اسم المستخدم</label>
                    <select id="login-user" class="w-full p-2 border rounded">
                        <option value="admin">المدير</option>
                        <option value="employee">موظف</option>
                    </select>
                </div>
                <div>
                    <label class="block mb-1">كلمة السر</label>
                    <input type="password" id="login-pass" class="w-full p-2 border rounded" placeholder="****">
                </div>
                <button onclick="handleLogin()" class="w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700 transition">دخول</button>
            </div>
        </div>
    </div>

    <!-- Main App Layout (Hidden until login) -->
    <div id="main-app" class="hidden flex flex-col h-screen">
        <!-- Header -->
        <header class="bg-blue-600 text-white p-4 shadow-md no-print flex justify-between items-center">
            <div class="flex items-center gap-4">
                <h2 class="text-xl font-bold">محل الساحل</h2>
                <span id="user-badge" class="bg-blue-800 px-2 py-1 rounded text-sm">المدير</span>
            </div>
            <nav class="flex gap-4 overflow-x-auto">
                <button onclick="showModule('pos')" class="hover:underline">نقطة البيع</button>
                <button onclick="showModule('returns')" class="hover:underline">الترجيع</button>
                <button onclick="showModule('inventory')" id="nav-inventory" class="hover:underline">المخزون</button>
                <button onclick="showModule('purchases')" id="nav-purchases" class="hover:underline">المشتريات</button>
                <button onclick="showModule('reports')" id="nav-reports" class="hover:underline">التقارير</button>
                <button onclick="logout()" class="bg-red-500 px-3 py-1 rounded">خروج</button>
            </nav>
        </header>

        <!-- Main Content -->
        <main class="flex-1 overflow-auto p-4">
            
            <!-- POS Module -->
            <div id="mod-pos" class="module grid grid-cols-1 lg:grid-cols-3 gap-6">
                <!-- Products Selection -->
                <div class="lg:col-span-2 space-y-4">
                    <div class="flex gap-2 no-print">
                        <input type="text" id="pos-search" oninput="filterProducts()" placeholder="ابحث عن منتج..." class="flex-1 p-3 border rounded shadow-sm">
                        <button onclick="startScanner('pos')" class="bg-green-600 text-white px-4 py-2 rounded flex items-center gap-2">
                            <span>📷</span> مسح
                        </button>
                    </div>
                    <div id="pos-camera-container" class="hidden mb-4 rounded-lg overflow-hidden border-2 border-green-500 h-64">
                        <div id="pos-reader"></div>
                    </div>
                    <div id="pos-product-list" class="grid grid-cols-2 md:grid-cols-4 gap-3">
                        <!-- Products rendered here -->
                    </div>
                </div>
                <!-- Cart -->
                <div class="bg-white p-4 rounded-xl shadow-md flex flex-col h-full">
                    <h3 class="text-lg font-bold border-b pb-2 mb-2 text-center">الفاتورة الحالية</h3>
                    <div id="pos-cart-items" class="flex-1 overflow-y-auto space-y-2 mb-4 min-h-[300px]">
                        <!-- Cart items -->
                    </div>
                    <div class="border-t pt-4">
                        <div class="flex justify-between text-xl font-bold mb-4">
                            <span>الإجمالي:</span>
                            <span id="pos-total">0.000</span><span> د.ل</span>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-2">
                            <button onclick="checkout('cash')" class="bg-blue-600 text-white py-3 rounded font-bold">نقداً (F5)</button>
                            <button onclick="showCardModal()" class="bg-purple-600 text-white py-3 rounded font-bold">بطاقة</button>
                        </div>
                        <button onclick="clearCart()" class="w-full text-red-500 py-2 border border-red-500 rounded">إلغاء</button>
                    </div>
                </div>
            </div>

            <!-- Returns Module -->
            <div id="mod-returns" class="module hidden">
                <div class="max-w-4xl mx-auto bg-white p-6 rounded shadow">
                    <h2 class="text-2xl font-bold mb-4">نقطة الترجيع</h2>
                    <div class="flex gap-2 mb-4">
                        <input type="text" id="return-invoice-id" placeholder="رقم الفاتورة..." class="flex-1 p-2 border rounded">
                        <button onclick="searchInvoice()" class="bg-blue-600 text-white px-6 py-2 rounded">بحث</button>
                    </div>
                    <div id="return-details" class="hidden">
                        <!-- Invoice data for return -->
                    </div>
                </div>
            </div>

            <!-- Inventory Module -->
            <div id="mod-inventory" class="module hidden">
                <div class="bg-white p-6 rounded shadow">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-2xl font-bold">المخزون وبطاقة الصنف</h2>
                        <button onclick="openProductModal()" class="bg-green-600 text-white px-4 py-2 rounded">إضافة صنف جديد</button>
                    </div>
                    <table class="w-full text-right border-collapse">
                        <thead>
                            <tr class="bg-gray-100">
                                <th class="p-2 border">باركود</th>
                                <th class="p-2 border">الاسم</th>
                                <th class="p-2 border">الكمية</th>
                                <th class="p-2 border">سعر البيع</th>
                                <th class="p-2 border">النوع</th>
                                <th class="p-2 border">إجراءات</th>
                            </tr>
                        </thead>
                        <tbody id="inventory-table-body">
                            <!-- Inventory items -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- Purchases Module -->
            <div id="mod-purchases" class="module hidden">
                <div class="bg-white p-6 rounded shadow max-w-2xl mx-auto">
                    <h2 class="text-2xl font-bold mb-4">تسجيل مشتريات (توريد)</h2>
                    <div class="space-y-4">
                        <select id="purchase-product-select" class="w-full p-2 border rounded">
                            <!-- Loaded from inventory -->
                        </select>
                        <div class="grid grid-cols-2 gap-4">
                            <input type="number" id="purchase-qty" placeholder="الكمية" class="p-2 border rounded">
                            <input type="number" id="purchase-cost" placeholder="سعر التكلفة" class="p-2 border rounded">
                        </div>
                        <button onclick="savePurchase()" class="w-full bg-blue-600 text-white py-2 rounded">تأكيد التوريد</button>
                    </div>
                </div>
            </div>

            <!-- Reports Module -->
            <div id="mod-reports" class="module hidden">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                    <div class="bg-white p-4 rounded shadow border-r-4 border-blue-500">
                        <h4 class="text-gray-500">مبيعات اليوم</h4>
                        <p id="report-today" class="text-2xl font-bold">0.000 د.ل</p>
                    </div>
                    <div class="bg-white p-4 rounded shadow border-r-4 border-green-500">
                        <h4 class="text-gray-500">مبيعات الشهر</h4>
                        <p id="report-month" class="text-2xl font-bold">0.000 د.ل</p>
                    </div>
                    <div class="bg-white p-4 rounded shadow border-r-4 border-yellow-500">
                        <h4 class="text-gray-500">إجمالي المخزون</h4>
                        <p id="report-stock-value" class="text-2xl font-bold">0.000 د.ل</p>
                    </div>
                </div>
                <div class="bg-white p-6 rounded shadow">
                    <canvas id="salesChart" height="100"></canvas>
                </div>
            </div>

        </main>
    </div>

    <!-- Modals -->
    <!-- Card Payment Modal -->
    <div id="card-modal" class="fixed inset-0 bg-black/50 hidden flex items-center justify-center p-4">
        <div class="bg-white p-6 rounded-lg w-full max-w-sm">
            <h3 class="text-lg font-bold mb-4">الدفع بالبطاقة</h3>
            <input type="text" id="card-auth-code" placeholder="رقم التفويض..." class="w-full p-3 border rounded mb-4">
            <div class="flex gap-2">
                <button onclick="checkout('card')" class="flex-1 bg-blue-600 text-white py-2 rounded">تأكيد</button>
                <button onclick="closeModal('card-modal')" class="flex-1 border py-2 rounded">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Product Modal -->
    <div id="product-modal" class="fixed inset-0 bg-black/50 hidden flex items-center justify-center p-4">
        <div class="bg-white p-6 rounded-lg w-full max-w-md">
            <h3 id="product-modal-title" class="text-lg font-bold mb-4">إضافة صنف</h3>
            <div class="space-y-3">
                <input type="text" id="prod-barcode" placeholder="الباركود" class="w-full p-2 border rounded">
                <input type="text" id="prod-name" placeholder="اسم المنتج" class="w-full p-2 border rounded">
                <div class="grid grid-cols-2 gap-2">
                    <input type="number" step="0.001" id="prod-price" placeholder="سعر البيع" class="p-2 border rounded">
                    <input type="number" step="0.001" id="prod-qty" placeholder="الكمية الحالية" class="p-2 border rounded">
                </div>
                <select id="prod-type" class="w-full p-2 border rounded">
                    <option value="unit">بالوحدة (عدد)</option>
                    <option value="weight">بالوزن (كيلو)</option>
                </select>
                <div class="flex gap-2">
                    <button onclick="saveProduct()" class="flex-1 bg-green-600 text-white py-2 rounded">حفظ</button>
                    <button onclick="closeModal('product-modal')" class="flex-1 border py-2 rounded">إلغاء</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Weight Entry Modal -->
    <div id="weight-modal" class="fixed inset-0 bg-black/50 hidden flex items-center justify-center p-4">
        <div class="bg-white p-6 rounded-lg w-full max-w-sm">
            <h3 id="weight-modal-title" class="text-lg font-bold mb-2">إدخال الوزن</h3>
            <p id="weight-unit-price" class="text-sm text-gray-500 mb-4"></p>
            <input type="number" step="0.001" id="pos-weight-input" placeholder="0.000 كجم" class="w-full text-3xl text-center p-3 border rounded mb-4">
            <div class="flex gap-2">
                <button id="weight-confirm-btn" class="flex-1 bg-blue-600 text-white py-2 rounded">إضافة</button>
                <button onclick="closeModal('weight-modal')" class="flex-1 border py-2 rounded">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Receipt Print Template -->
    <div id="receipt-print" class="print-only text-center p-4 text-sm" style="width: 80mm;">
        <h2 class="text-lg font-bold">محل الساحل للمواد الغذائية</h2>
        <p>شارع الساحل - طرابلس</p>
        <p>-------------------------</p>
        <div id="receipt-items" class="text-right"></div>
        <p>-------------------------</p>
        <div id="receipt-totals" class="font-bold text-right"></div>
        <p class="mt-4">شكراً لزيارتكم</p>
        <p id="receipt-footer" class="text-xs"></p>
    </div>

    <script>
        // Data Store
        let state = {
            currentUser: null,
            products: JSON.parse(localStorage.getItem('al-sahel-products')) || [
                { id: '1', barcode: '1001', name: 'سكر 1كجم', price: 3.5, qty: 100, type: 'unit' },
                { id: '2', barcode: '1002', name: 'زيت ذرة', price: 7.25, qty: 50, type: 'unit' },
                { id: '3', barcode: '1003', name: 'عدس (وزن)', price: 4.0, qty: 25.5, type: 'weight' }
            ],
            cart: [],
            sales: JSON.parse(localStorage.getItem('al-sahel-sales')) || [],
            purchases: JSON.parse(localStorage.getItem('al-sahel-purchases')) || []
        };

        const USERS = {
            admin: '1234',
            employee: '0000'
        };

        // --- Auth ---
        function handleLogin() {
            const role = document.getElementById('login-user').value;
            const pass = document.getElementById('login-pass').value;
            
            if (USERS[role] === pass) {
                state.currentUser = role;
                document.getElementById('login-screen').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
                document.getElementById('user-badge').innerText = role === 'admin' ? 'المدير' : 'موظف';
                
                // Hide restricted tabs for employee
                if (role === 'employee') {
                    document.getElementById('nav-inventory').classList.add('hidden');
                    document.getElementById('nav-purchases').classList.add('hidden');
                    document.getElementById('nav-reports').classList.add('hidden');
                } else {
                    document.getElementById('nav-inventory').classList.remove('hidden');
                    document.getElementById('nav-purchases').classList.remove('hidden');
                    document.getElementById('nav-reports').classList.remove('hidden');
                }

                showModule('pos');
                renderProducts();
                renderPurchasesList();
            } else {
                alert('كلمة مرور خاطئة');
            }
        }

        function logout() {
            state.currentUser = null;
            document.getElementById('main-app').classList.add('hidden');
            document.getElementById('login-screen').classList.remove('hidden');
            document.getElementById('login-pass').value = '';
        }

        // --- Navigation ---
        function showModule(modId) {
            document.querySelectorAll('.module').forEach(m => m.classList.add('hidden'));
            document.getElementById(`mod-${modId}`).classList.remove('hidden');
            if (modId === 'reports') renderReports();
            if (modId === 'inventory') renderInventory();
        }

        // --- POS Logic ---
        function renderProducts() {
            const list = document.getElementById('pos-product-list');
            list.innerHTML = '';
            state.products.forEach(p => {
                const div = document.createElement('div');
                div.className = "bg-white p-3 rounded-lg shadow-sm border hover:border-blue-500 cursor-pointer text-center";
                div.onclick = () => addToCart(p.id);
                div.innerHTML = `
                    <div class="font-bold">${p.name}</div>
                    <div class="text-blue-600 font-bold">${p.price.toFixed(3)} د.ل</div>
                    <div class="text-xs text-gray-500">${p.type === 'weight' ? 'بالكيلو' : 'بالقطعة'}</div>
                `;
                list.appendChild(div);
            });
        }

        function filterProducts() {
            const query = document.getElementById('pos-search').value.toLowerCase();
            const filtered = state.products.filter(p => 
                p.name.toLowerCase().includes(query) || p.barcode.includes(query)
            );
            const list = document.getElementById('pos-product-list');
            list.innerHTML = '';
            filtered.forEach(p => {
                const div = document.createElement('div');
                div.className = "bg-white p-3 rounded-lg shadow-sm border hover:border-blue-500 cursor-pointer text-center";
                div.onclick = () => addToCart(p.id);
                div.innerHTML = `
                    <div class="font-bold">${p.name}</div>
                    <div class="text-blue-600 font-bold">${p.price.toFixed(3)} د.ل</div>
                    <div class="text-xs text-gray-500">${p.type === 'weight' ? 'بالكيلو' : 'بالقطعة'}</div>
                `;
                list.appendChild(div);
            });
        }

        function addToCart(productId) {
            const product = state.products.find(p => p.id === productId);
            if (!product) return;

            if (product.type === 'weight') {
                document.getElementById('weight-modal-title').innerText = `إدخال وزن: ${product.name}`;
                document.getElementById('weight-unit-price').innerText = `سعر الكيلو: ${product.price.toFixed(3)} د.ل`;
                document.getElementById('pos-weight-input').value = '';
                document.getElementById('weight-modal').classList.remove('hidden');
                document.getElementById('weight-confirm-btn').onclick = () => {
                    const weight = parseFloat(document.getElementById('pos-weight-input').value);
                    if (weight > 0) {
                        processAddToCart(product, weight);
                        closeModal('weight-modal');
                    }
                };
            } else {
                processAddToCart(product, 1);
            }
        }

        function processAddToCart(product, qty) {
            const existing = state.cart.find(item => item.id === product.id);
            if (existing && product.type === 'unit') {
                existing.qty += qty;
            } else {
                state.cart.push({ ...product, qty: qty });
            }
            updateCartUI();
        }

        function updateCartUI() {
            const container = document.getElementById('pos-cart-items');
            container.innerHTML = '';
            let total = 0;

            state.cart.forEach((item, index) => {
                const subtotal = item.price * item.qty;
                total += subtotal;
                const div = document.createElement('div');
                div.className = "flex justify-between items-center p-2 bg-gray-50 rounded text-sm";
                div.innerHTML = `
                    <div class="flex-1">
                        <div class="font-bold">${item.name}</div>
                        <div class="text-xs text-gray-500">${item.qty} ${item.type === 'weight' ? 'كجم' : 'وحدة'} × ${item.price.toFixed(3)}</div>
                    </div>
                    <div class="font-bold text-blue-600 ml-4">${subtotal.toFixed(3)}</div>
                    <button onclick="removeFromCart(${index})" class="text-red-500 font-bold px-2">×</button>
                `;
                container.appendChild(div);
            });

            document.getElementById('pos-total').innerText = total.toFixed(3);
        }

        function removeFromCart(index) {
            state.cart.splice(index, 1);
            updateCartUI();
        }

        function clearCart() {
            state.cart = [];
            updateCartUI();
        }

        // --- Payments & F5 ---
        function showCardModal() {
            if (state.cart.length === 0) return;
            document.getElementById('card-modal').classList.remove('hidden');
        }

        function checkout(method) {
            if (state.cart.length === 0) return;
            
            const total = state.cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            const authCode = document.getElementById('card-auth-code').value;
            
            const transaction = {
                id: 'INV-' + Date.now(),
                date: new Date().toISOString(),
                user: state.currentUser,
                items: [...state.cart],
                total: total,
                method: method,
                authCode: method === 'card' ? authCode : null
            };

            // Deduct stock
            state.cart.forEach(item => {
                const p = state.products.find(prod => prod.id === item.id);
                if (p) p.qty -= item.qty;
            });

            state.sales.push(transaction);
            saveData();
            
            printInvoice(transaction);
            
            // Reset
            clearCart();
            document.getElementById('card-auth-code').value = '';
            closeModal('card-modal');
            renderProducts();
            alert('تمت العملية بنجاح. رقم الفاتورة: ' + transaction.id);
        }

        // F5 Keyboard Shortcut
        window.addEventListener('keydown', (e) => {
            if (e.key === 'F5') {
                e.preventDefault();
                if (!document.getElementById('mod-pos').classList.contains('hidden')) {
                    checkout('cash');
                }
            }
        });

        // --- Inventory Management ---
        function renderInventory() {
            const body = document.getElementById('inventory-table-body');
            body.innerHTML = '';
            state.products.forEach(p => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td class="p-2 border">${p.barcode}</td>
                    <td class="p-2 border font-bold">${p.name}</td>
                    <td class="p-2 border ${p.qty < 10 ? 'text-red-600 font-bold' : ''}">${p.qty}</td>
                    <td class="p-2 border">${p.price.toFixed(3)}</td>
                    <td class="p-2 border">${p.type === 'weight' ? 'وزن' : 'وحدة'}</td>
                    <td class="p-2 border">
                        <button onclick="editProduct('${p.id}')" class="text-blue-600 px-2">تعديل</button>
                    </td>
                `;
                body.appendChild(row);
            });
            updatePurchaseSelect();
        }

        function openProductModal(id = null) {
            if (id) {
                // Edit mode
            } else {
                document.getElementById('product-modal-title').innerText = "إضافة صنف جديد";
                document.getElementById('prod-barcode').value = '';
                document.getElementById('prod-name').value = '';
                document.getElementById('prod-price').value = '';
                document.getElementById('prod-qty').value = '';
            }
            document.getElementById('product-modal').classList.remove('hidden');
        }

        function saveProduct() {
            const product = {
                id: Date.now().toString(),
                barcode: document.getElementById('prod-barcode').value,
                name: document.getElementById('prod-name').value,
                price: parseFloat(document.getElementById('prod-price').value),
                qty: parseFloat(document.getElementById('prod-qty').value),
                type: document.getElementById('prod-type').value
            };

            if (!product.barcode || !product.name || isNaN(product.price)) {
                alert('يرجى ملء كافة البيانات');
                return;
            }

            state.products.push(product);
            saveData();
            renderInventory();
            renderProducts();
            closeModal('product-modal');
        }

        // --- Purchases ---
        function updatePurchaseSelect() {
            const select = document.getElementById('purchase-product-select');
            select.innerHTML = '<option value="">اختر المنتج...</option>';
            state.products.forEach(p => {
                const opt = document.createElement('option');
                opt.value = p.id;
                opt.textContent = p.name;
                select.appendChild(opt);
            });
        }

        function savePurchase() {
            const prodId = document.getElementById('purchase-product-select').value;
            const qty = parseFloat(document.getElementById('purchase-qty').value);
            const cost = parseFloat(document.getElementById('purchase-cost').value);

            if (!prodId || isNaN(qty) || isNaN(cost)) return;

            const product = state.products.find(p => p.id === prodId);
            product.qty += qty;

            state.purchases.push({
                date: new Date().toISOString(),
                productName: product.name,
                qty: qty,
                cost: cost
            });

            saveData();
            alert('تم توريد الكمية');
            document.getElementById('purchase-qty').value = '';
            document.getElementById('purchase-cost').value = '';
        }

        // --- Reports ---
        function renderReports() {
            const today = new Date().toISOString().split('T')[0];
            const month = today.substring(0, 7);

            const salesToday = state.sales
                .filter(s => s.date.startsWith(today))
                .reduce((sum, s) => sum + s.total, 0);

            const salesMonth = state.sales
                .filter(s => s.date.startsWith(month))
                .reduce((sum, s) => sum + s.total, 0);

            const stockValue = state.products
                .reduce((sum, p) => sum + (p.qty * p.price), 0);

            document.getElementById('report-today').innerText = salesToday.toFixed(3) + ' د.ل';
            document.getElementById('report-month').innerText = salesMonth.toFixed(3) + ' د.ل';
            document.getElementById('report-stock-value').innerText = stockValue.toFixed(3) + ' د.ل';

            // Chart
            const ctx = document.getElementById('salesChart').getContext('2d');
            
            // Simple logic for last 7 days chart
            const labels = [];
            const data = [];
            for(let i=6; i>=0; i--) {
                const d = new Date();
                d.setDate(d.getDate() - i);
                const dayStr = d.toISOString().split('T')[0];
                labels.push(dayStr);
                const val = state.sales
                    .filter(s => s.date.startsWith(dayStr))
                    .reduce((sum, s) => sum + s.total, 0);
                data.push(val);
            }

            if (window.myChart) window.myChart.destroy();
            window.myChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: labels,
                    datasets: [{
                        label: 'مبيعات آخر 7 أيام',
                        data: data,
                        borderColor: '#2563eb',
                        tension: 0.1,
                        fill: true,
                        backgroundColor: 'rgba(37, 99, 235, 0.1)'
                    }]
                }
            });
        }

        // --- Returns ---
        function searchInvoice() {
            const id = document.getElementById('return-invoice-id').value;
            const invoice = state.sales.find(s => s.id === id);
            const container = document.getElementById('return-details');
            
            if (invoice) {
                container.innerHTML = `
                    <div class="mt-4 border p-4 rounded">
                        <div class="flex justify-between mb-4">
                            <span>التاريخ: ${new Date(invoice.date).toLocaleString()}</span>
                            <span>الإجمالي: ${invoice.total.toFixed(3)} د.ل</span>
                        </div>
                        <div class="space-y-2">
                            ${invoice.items.map(item => `
                                <div class="flex justify-between border-b pb-1">
                                    <span>${item.name} (${item.qty})</span>
                                    <button onclick="processReturn('${invoice.id}', '${item.id}')" class="text-red-500 text-xs">ترجيع</button>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                `;
                container.classList.remove('hidden');
            } else {
                alert('الفاتورة غير موجودة');
            }
        }

        function processReturn(invId, itemId) {
            if (!confirm('هل أنت متأكد من إرجاع الصنف؟')) return;
            
            const invoice = state.sales.find(s => s.id === invId);
            const itemIdx = invoice.items.findIndex(i => i.id === itemId);
            const item = invoice.items[itemIdx];

            // Add back to stock
            const prod = state.products.find(p => p.id === item.id);
            if (prod) prod.qty += item.qty;

            // Reduce invoice total (simple logic: remove item entirely)
            invoice.total -= (item.price * item.qty);
            invoice.items.splice(itemIdx, 1);

            saveData();
            searchInvoice();
            alert('تم إرجاع الصنف بنجاح');
        }

        // --- Utilities ---
        function saveData() {
            localStorage.setItem('al-sahel-products', JSON.stringify(state.products));
            localStorage.setItem('al-sahel-sales', JSON.stringify(state.sales));
            localStorage.setItem('al-sahel-purchases', JSON.stringify(state.purchases));
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        function printInvoice(transaction) {
            const itemsDiv = document.getElementById('receipt-items');
            itemsDiv.innerHTML = '';
            transaction.items.forEach(item => {
                itemsDiv.innerHTML += `
                    <div class="flex justify-between">
                        <span>${item.name}</span>
                        <span>${(item.price * item.qty).toFixed(3)}</span>
                    </div>
                    <div class="text-xs">${item.qty} × ${item.price.toFixed(3)}</div>
                `;
            });

            document.getElementById('receipt-totals').innerHTML = `
                <div class="flex justify-between mt-2">
                    <span>الإجمالي:</span>
                    <span>${transaction.total.toFixed(3)} د.ل</span>
                </div>
                <div class="text-xs font-normal">طريقة الدفع: ${transaction.method === 'cash' ? 'نقداً' : 'بطاقة'}</div>
                ${transaction.authCode ? `<div class="text-xs font-normal">رقم التفويض: ${transaction.authCode}</div>` : ''}
            `;

            document.getElementById('receipt-footer').innerText = `رقم الفاتورة: ${transaction.id}\nالتاريخ: ${new Date(transaction.date).toLocaleString()}`;
            
            window.print();
        }

        // --- Scanner Integration ---
        let html5QrCode = null;
        function startScanner(mod) {
            const container = document.getElementById(`${mod}-camera-container`);
            container.classList.toggle('hidden');
            
            if (container.classList.contains('hidden')) {
                if (html5QrCode) html5QrCode.stop();
                return;
            }

            html5QrCode = new Html5Qrcode(`${mod}-reader`);
            html5QrCode.start(
                { facingMode: "environment" }, 
                { fps: 10, qrbox: { width: 250, height: 150 } },
                (decodedText) => {
                    // Success
                    const product = state.products.find(p => p.barcode === decodedText);
                    if (product) {
                        addToCart(product.id);
                        html5QrCode.stop();
                        container.classList.add('hidden');
                    }
                },
                (errorMessage) => {}
            ).catch(err => {
                console.error(err);
                alert('لا يمكن تشغيل الكاميرا');
                container.classList.add('hidden');
            });
        }

    </script>
</body>
</html> 
