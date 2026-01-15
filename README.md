<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منظومة الساحل للمواد الغذائية</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@200;300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Cairo', sans-serif;
        }
        .hide {
            display: none;
        }
        /* Custom scrollbar for cleaner look */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1; 
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1; 
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8; 
        }

        @media print {
            body * {
                visibility: hidden;
            }
            #receipt-modal, #receipt-modal * {
                visibility: visible;
            }
            #receipt-modal {
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
                height: 100%;
                background: white;
                display: block !important;
                z-index: 9999;
            }
            #receipt-modal .print\:hidden {
                display: none !important;
            }
            /* Remove shadows and rounded corners for print */
            #receipt-modal > div {
                box-shadow: none !important;
                border-radius: 0 !important;
                width: 100% !important;
                max-width: 100% !important;
            }
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 h-screen overflow-hidden flex">

    <!-- Sidebar -->
    <aside class="w-64 bg-slate-900 text-white flex flex-col shadow-xl z-20 transition-all duration-300" id="sidebar">
        <div class="p-6 flex items-center gap-3 border-b border-slate-700">
            <div class="w-10 h-10 bg-emerald-500 rounded-lg flex items-center justify-center text-white font-bold text-xl">
                <i class="fa-solid fa-basket-shopping"></i>
            </div>
            <div>
                <h1 class="text-lg font-bold leading-tight">محل الساحل</h1>
                <p class="text-xs text-slate-400">للمواد الغذائية</p>
            </div>
        </div>

        <nav class="flex-1 p-4 space-y-2 overflow-y-auto">
            <button onclick="showSection('pos')" id="btn-pos" class="nav-btn w-full flex items-center gap-3 p-3 rounded-lg hover:bg-emerald-600 transition-colors bg-emerald-600 text-white">
                <i class="fa-solid fa-cash-register w-6 text-center"></i>
                <span>نقطة البيع (POS)</span>
            </button>
            <button onclick="showSection('inventory')" id="btn-inventory" class="nav-btn w-full flex items-center gap-3 p-3 rounded-lg hover:bg-slate-700 transition-colors text-slate-300">
                <i class="fa-solid fa-boxes-stacked w-6 text-center"></i>
                <span>المخزون والمنتجات</span>
            </button>
            <button onclick="showSection('sales')" id="btn-sales" class="nav-btn w-full flex items-center gap-3 p-3 rounded-lg hover:bg-slate-700 transition-colors text-slate-300">
                <i class="fa-solid fa-file-invoice-dollar w-6 text-center"></i>
                <span>سجل المبيعات</span>
            </button>
            <button onclick="showSection('dashboard')" id="btn-dashboard" class="nav-btn w-full flex items-center gap-3 p-3 rounded-lg hover:bg-slate-700 transition-colors text-slate-300">
                <i class="fa-solid fa-chart-pie w-6 text-center"></i>
                <span>لوحة التحكم</span>
            </button>
        </nav>

        <div class="p-4 border-t border-slate-700">
            <button onclick="clearData()" class="w-full flex items-center gap-2 text-red-400 hover:text-red-300 text-sm p-2">
                <i class="fa-solid fa-trash"></i>
                <span>حذف جميع البيانات</span>
            </button>
        </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 flex flex-col h-screen overflow-hidden relative">
        <!-- Header -->
        <header class="h-16 bg-white shadow-sm flex items-center justify-between px-6 z-10">
            <h2 id="page-title" class="text-xl font-bold text-slate-700">نقطة البيع</h2>
            <div class="flex items-center gap-4">
                <div class="text-sm text-slate-500 bg-slate-100 px-3 py-1 rounded-full">
                    <i class="fa-regular fa-calendar ml-1"></i>
                    <span id="current-date"></span>
                </div>
            </div>
        </header>

        <!-- Content Sections -->
        <div class="flex-1 overflow-auto bg-slate-100 p-6 relative">
            
            <!-- 1. POS Section -->
            <section id="pos-section" class="flex gap-4 h-full">
                <!-- Product List (Left) -->
                <div class="flex-1 flex flex-col gap-4">
                    <!-- Search -->
                    <div class="bg-white p-4 rounded-xl shadow-sm flex gap-2">
                        <div class="relative flex-1">
                            <i class="fa-solid fa-search absolute right-3 top-3 text-slate-400"></i>
                            <input type="text" id="pos-search" placeholder="ابحث عن منتج بالاسم أو الباركود..." class="w-full pr-10 pl-4 py-2 bg-slate-50 border border-slate-200 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500 transition-all">
                        </div>
                        <select id="pos-category-filter" class="p-2 border border-slate-200 rounded-lg bg-slate-50 focus:outline-none">
                            <option value="all">الكل</option>
                            <option value="food">مواد غذائية</option>
                            <option value="drinks">مشروبات</option>
                            <option value="cleaning">منظفات</option>
                            <option value="vegetables">خضروات وفواكه</option>
                        </select>
                    </div>
                    
                    <!-- Grid -->
                    <div id="pos-products-grid" class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 overflow-y-auto pr-1 pb-2">
                        <!-- Products injected here JS -->
                    </div>
                </div>

                <!-- Cart (Right) -->
                <div class="w-96 bg-white rounded-xl shadow-sm flex flex-col h-full border border-slate-200">
                    <div class="p-4 border-b border-slate-100 bg-emerald-50 rounded-t-xl">
                        <h3 class="font-bold text-emerald-800 flex items-center gap-2">
                            <i class="fa-solid fa-cart-shopping"></i> سلة المشتريات
                        </h3>
                    </div>
                    
                    <div class="flex-1 overflow-y-auto p-2 space-y-2" id="cart-items">
                        <!-- Cart Items injected JS -->
                        <div class="h-full flex flex-col items-center justify-center text-slate-400">
                            <i class="fa-solid fa-basket-shopping text-4xl mb-2"></i>
                            <p>السلة فارغة</p>
                        </div>
                    </div>

                    <div class="p-4 bg-slate-50 border-t border-slate-200 rounded-b-xl space-y-3">
                        <div class="flex justify-between text-sm text-slate-600">
                            <span>عدد العناصر:</span>
                            <span id="cart-count" class="font-bold">0</span>
                        </div>
                        <div class="flex justify-between text-xl font-bold text-slate-800">
                            <span>الإجمالي:</span>
                            <span class="text-emerald-600"><span id="cart-total">0.00</span> د.ل</span>
                        </div>
                        <button onclick="checkout()" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-lg font-bold shadow-lg shadow-emerald-200 transition-all flex justify-center items-center gap-2">
                            <i class="fa-solid fa-check"></i> إتمام البيع
                        </button>
                    </div>
                </div>
            </section>

            <!-- 2. Inventory Section -->
            <section id="inventory-section" class="hide h-full flex flex-col gap-4">
                <div class="flex justify-between items-center bg-white p-4 rounded-xl shadow-sm">
                    <h3 class="font-bold text-lg">إدارة المخزون</h3>
                    <button onclick="openModal('add-product-modal')" class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg flex items-center gap-2 shadow-md transition-all">
                        <i class="fa-solid fa-plus"></i> إضافة منتج جديد
                    </button>
                </div>

                <div class="bg-white rounded-xl shadow-sm border border-slate-200 flex-1 overflow-hidden flex flex-col">
                    <div class="p-4 border-b border-slate-100 flex gap-4">
                        <input type="text" id="inventory-search" placeholder="بحث في المخزون..." class="flex-1 p-2 border border-slate-200 rounded-lg bg-slate-50">
                    </div>
                    <div class="overflow-auto flex-1">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 text-slate-600 sticky top-0">
                                <tr>
                                    <th class="p-4 font-semibold">اسم المنتج</th>
                                    <th class="p-4 font-semibold">القسم</th>
                                    <th class="p-4 font-semibold">الباركود</th>
                                    <th class="p-4 font-semibold">الوحدة</th>
                                    <th class="p-4 font-semibold">السعر</th>
                                    <th class="p-4 font-semibold">الكمية</th>
                                    <th class="p-4 font-semibold">انتهاء الصلاحية</th>
                                    <th class="p-4 font-semibold text-center">إجراءات</th>
                                </tr>
                            </thead>
                            <tbody id="inventory-table-body" class="divide-y divide-slate-100">
                                <!-- Table rows via JS -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>

            <!-- 3. Sales History Section -->
            <section id="sales-section" class="hide h-full flex flex-col gap-4">
                <div class="bg-white p-4 rounded-xl shadow-sm">
                    <h3 class="font-bold text-lg">سجل الفواتير والمبيعات</h3>
                </div>
                <div class="bg-white rounded-xl shadow-sm border border-slate-200 flex-1 overflow-hidden flex flex-col">
                    <div class="overflow-auto flex-1">
                        <table class="w-full text-right">
                            <thead class="bg-slate-50 text-slate-600 sticky top-0">
                                <tr>
                                    <th class="p-4 font-semibold">رقم الفاتورة</th>
                                    <th class="p-4 font-semibold">التاريخ والوقت</th>
                                    <th class="p-4 font-semibold">عدد الأصناف</th>
                                    <th class="p-4 font-semibold">الإجمالي</th>
                                    <th class="p-4 font-semibold text-center">التفاصيل</th>
                                </tr>
                            </thead>
                            <tbody id="sales-table-body" class="divide-y divide-slate-100">
                                <!-- Sales rows via JS -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>

             <!-- 4. Dashboard Section -->
             <section id="dashboard-section" class="hide h-full overflow-y-auto">
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-6">
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100 flex items-center gap-4">
                        <div class="w-12 h-12 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center text-xl">
                            <i class="fa-solid fa-coins"></i>
                        </div>
                        <div>
                            <p class="text-sm text-slate-500">إجمالي المبيعات اليوم</p>
                            <h4 class="text-2xl font-bold" id="dash-total-sales">0.00 د.ل</h4>
                        </div>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100 flex items-center gap-4">
                        <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-full flex items-center justify-center text-xl">
                            <i class="fa-solid fa-receipt"></i>
                        </div>
                        <div>
                            <p class="text-sm text-slate-500">عدد الفواتير</p>
                            <h4 class="text-2xl font-bold" id="dash-invoice-count">0</h4>
                        </div>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100 flex items-center gap-4">
                        <div class="w-12 h-12 bg-amber-100 text-amber-600 rounded-full flex items-center justify-center text-xl">
                            <i class="fa-solid fa-box"></i>
                        </div>
                        <div>
                            <p class="text-sm text-slate-500">عدد المنتجات</p>
                            <h4 class="text-2xl font-bold" id="dash-product-count">0</h4>
                        </div>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100 flex items-center gap-4">
                        <div class="w-12 h-12 bg-red-100 text-red-600 rounded-full flex items-center justify-center text-xl">
                            <i class="fa-solid fa-triangle-exclamation"></i>
                        </div>
                        <div>
                            <p class="text-sm text-slate-500">منتهية الصلاحية قريباً</p>
                            <h4 class="text-2xl font-bold" id="dash-expiry-count">0</h4>
                        </div>
                    </div>
                </div>

                <!-- Recent Sales Chart Placeholder (Optional visualization) -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100 mb-6">
                    <h3 class="font-bold text-lg mb-4">أحدث العمليات</h3>
                    <div id="dash-recent-sales" class="space-y-3">
                        <!-- Recent list -->
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- Modals -->

    <!-- Add Product Modal -->
    <div id="add-product-modal" class="fixed inset-0 bg-black/50 z-50 hidden flex items-center justify-center backdrop-blur-sm">
        <div class="bg-white rounded-2xl w-full max-w-lg shadow-2xl transform transition-all scale-100 p-6">
            <div class="flex justify-between items-center mb-6 border-b border-slate-100 pb-4">
                <h3 class="text-xl font-bold text-slate-800">إضافة منتج جديد</h3>
                <button onclick="closeModal('add-product-modal')" class="text-slate-400 hover:text-red-500 transition-colors">
                    <i class="fa-solid fa-times text-xl"></i>
                </button>
            </div>
            
            <form id="add-product-form" onsubmit="handleProductSubmit(event)" class="space-y-4">
                <div class="grid grid-cols-2 gap-4">
                    <div class="col-span-2">
                        <label class="block text-sm font-medium text-slate-700 mb-1">اسم المنتج</label>
                        <input type="text" name="name" required class="w-full p-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-1">السعر (د.ل)</label>
                        <input type="number" step="0.01" name="price" required class="w-full p-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-1">الوحدة</label>
                        <select name="unit" class="w-full p-2 border border-slate-300 rounded-lg bg-white focus:ring-2 focus:ring-blue-500 outline-none">
                            <option value="piece">قطعة</option>
                            <option value="kg">كيلوجرام (وزن)</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-1">القسم</label>
                        <select name="category" class="w-full p-2 border border-slate-300 rounded-lg bg-white focus:ring-2 focus:ring-blue-500 outline-none">
                            <option value="food">مواد غذائية</option>
                            <option value="drinks">مشروبات</option>
                            <option value="cleaning">منظفات</option>
                            <option value="vegetables">بقوليات</option>
                            <option value="other">أخرى</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-1">الكمية المخزنة</label>
                        <input type="number" name="stock" value="100" class="w-full p-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                    </div>
                    <div class="col-span-2">
                        <label class="block text-sm font-medium text-slate-700 mb-1">تاريخ انتهاء الصلاحية</label>
                        <input type="date" name="expiry" required class="w-full p-2 border border-slate-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                    </div>
                </div>
                
                <div class="flex justify-end gap-3 mt-6 pt-4 border-t border-slate-100">
                    <button type="button" onclick="closeModal('add-product-modal')" class="px-4 py-2 text-slate-600 hover:bg-slate-100 rounded-lg">إلغاء</button>
                    <button type="submit" class="px-6 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 shadow-lg shadow-blue-200">حفظ المنتج</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Weight Input Modal -->
    <div id="weight-modal" class="fixed inset-0 bg-black/50 z-50 hidden flex items-center justify-center backdrop-blur-sm">
        <div class="bg-white rounded-2xl w-full max-w-sm shadow-2xl p-6 text-center">
            <div class="mb-4">
                <i class="fa-solid fa-scale-balanced text-4xl text-emerald-500"></i>
            </div>
            <h3 class="text-xl font-bold text-slate-800 mb-2">تحديد الوزن</h3>
            <p class="text-slate-500 mb-4" id="weight-product-name">اسم المنتج</p>
            
            <div class="flex items-center justify-center gap-2 mb-6">
                <input type="number" id="weight-input" step="0.05" placeholder="0.000" class="text-center text-2xl font-bold w-32 p-2 border-b-2 border-emerald-500 focus:outline-none">
                <span class="text-lg font-bold text-slate-400">كجم</span>
            </div>

            <div class="grid grid-cols-2 gap-3">
                <button onclick="confirmWeight()" class="bg-emerald-600 text-white py-2 rounded-lg hover:bg-emerald-700">تأكيد</button>
                <button onclick="closeModal('weight-modal')" class="bg-slate-200 text-slate-700 py-2 rounded-lg hover:bg-slate-300">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Receipt Modal -->
    <div id="receipt-modal" class="fixed inset-0 bg-black/50 z-50 hidden flex items-center justify-center backdrop-blur-sm">
        <div class="bg-white rounded-none md:rounded-lg w-full md:w-80 shadow-2xl p-6 text-center h-full md:h-auto overflow-y-auto">
            <div class="border-b-2 border-dashed border-slate-300 pb-4 mb-4">
                <h2 class="text-xl font-bold">محل الساحل للمواد الغذائية</h2>
                <p class="text-xs text-slate-500 mt-1">شارع أولاد خليفة</p>
                <p class="text-xs text-slate-500" id="receipt-date"></p>
                <p class="text-xs text-slate-500 mt-1">فاتورة رقم: <span id="receipt-id"></span></p>
            </div>
            
            <div id="receipt-items" class="text-sm space-y-2 mb-4 text-right">
                <!-- Items -->
            </div>

            <div class="border-t-2 border-dashed border-slate-300 pt-4 mb-6">
                <div class="flex justify-between font-bold text-lg">
                    <span>الإجمالي:</span>
                    <span id="receipt-total">0.00 د.ل</span>
                </div>
            </div>

            <button onclick="printReceipt()" class="w-full bg-slate-800 text-white py-2 rounded-lg hover:bg-slate-900 print:hidden">
                <i class="fa-solid fa-print"></i> طباعة الفاتورة
            </button>
            <button onclick="closeModal('receipt-modal')" class="w-full mt-2 text-slate-500 py-2 hover:text-slate-700 text-sm print:hidden">
                إغلاق
            </button>
        </div>
    </div>

    <script>
        // --- State Management ---
        let products = JSON.parse(localStorage.getItem('sahel_products')) || [
            { id: 1, name: "حليب المراعي 1 لتر", price: 5.50, unit: "piece", category: "drinks", stock: 50, expiry: "2024-12-31" },
            { id: 2, name: "أرز بسمتي", price: 7.00, unit: "kg", category: "food", stock: 100, expiry: "2025-06-30" },
            { id: 3, name: "جبنة موزاريلا", price: 35.00, unit: "kg", category: "food", stock: 20, expiry: "2024-02-20" }, // Near expiry example
            { id: 4, name: "عصير برتقال", price: 2.50, unit: "piece", category: "drinks", stock: 100, expiry: "2024-10-15" },
            { id: 5, name: "موز", price: 6.50, unit: "kg", category: "vegetables", stock: 50, expiry: "2024-01-20" },
            { id: 6, name: "صابون سائل", price: 12.00, unit: "piece", category: "cleaning", stock: 30, expiry: "2026-01-01" },
        ];
        
        let cart = [];
        let sales = JSON.parse(localStorage.getItem('sahel_sales')) || [];
        
        let tempWeightProductId = null;

        // --- Init ---
        document.addEventListener('DOMContentLoaded', () => {
            updateDate();
            renderProducts();
            renderInventory();
            updateDashboard();
            renderSalesHistory();

            // Search Listeners
            document.getElementById('pos-search').addEventListener('input', (e) => renderProducts(e.target.value));
            document.getElementById('pos-category-filter').addEventListener('change', () => renderProducts(document.getElementById('pos-search').value));
            document.getElementById('inventory-search').addEventListener('input', (e) => renderInventory(e.target.value));
        });

        function saveData() {
            localStorage.setItem('sahel_products', JSON.stringify(products));
            localStorage.setItem('sahel_sales', JSON.stringify(sales));
        }

        function clearData() {
            if(confirm('هل أنت متأكد من حذف جميع البيانات؟ لا يمكن التراجع.')) {
                localStorage.clear();
                location.reload();
            }
        }

        function updateDate() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('current-date').textContent = now.toLocaleDateString('ar-LY', options);
        }

        // --- Navigation ---
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('main section').forEach(el => el.classList.add('hide'));
            // Show target
            document.getElementById(`${sectionId}-section`).classList.remove('hide');
            
            // Update Sidebar Active State
            document.querySelectorAll('.nav-btn').forEach(el => {
                el.classList.remove('bg-emerald-600', 'text-white');
                el.classList.add('text-slate-300');
            });
            const activeBtn = document.getElementById(`btn-${sectionId}`);
            activeBtn.classList.remove('text-slate-300');
            activeBtn.classList.add('bg-emerald-600', 'text-white');

            // Update Title
            const titles = {
                'pos': 'نقطة البيع',
                'inventory': 'المخزون والمنتجات',
                'sales': 'سجل المبيعات',
                'dashboard': 'لوحة التحكم'
            };
            document.getElementById('page-title').textContent = titles[sectionId];
            
            if(sectionId === 'dashboard') updateDashboard();
            if(sectionId === 'sales') renderSalesHistory();
        }

        // --- POS Logic ---
        function renderProducts(searchTerm = '') {
            const grid = document.getElementById('pos-products-grid');
            grid.innerHTML = '';
            
            const categoryFilter = document.getElementById('pos-category-filter').value;

            const filtered = products.filter(p => {
                const matchesSearch = p.name.includes(searchTerm) || p.id.toString().includes(searchTerm);
                const matchesCategory = categoryFilter === 'all' || p.category === categoryFilter;
                return matchesSearch && matchesCategory;
            });

            filtered.forEach(p => {
                const isKg = p.unit === 'kg';
                const div = document.createElement('div');
                div.className = 'bg-white p-3 rounded-xl shadow-sm border border-slate-100 hover:shadow-md transition-all cursor-pointer flex flex-col items-center text-center group';
                div.onclick = () => initAddToCart(p.id);
                
                div.innerHTML = `
                    <div class="w-16 h-16 bg-slate-50 rounded-full flex items-center justify-center mb-2 text-2xl group-hover:bg-emerald-50 group-hover:text-emerald-600 transition-colors">
                        <i class="fa-solid ${getIcon(p.category)}"></i>
                    </div>
                    <h4 class="font-bold text-slate-800 text-sm mb-1 line-clamp-2 h-10 flex items-center justify-center">${p.name}</h4>
                    <div class="flex items-center gap-1 text-emerald-600 font-bold">
                        <span>${p.price.toFixed(2)}</span>
                        <span class="text-xs">د.ل / ${isKg ? 'كجم' : 'قطعة'}</span>
                    </div>
                `;
                grid.appendChild(div);
            });
        }

        function getIcon(category) {
            const icons = {
                'food': 'fa-bowl-food',
                'drinks': 'fa-bottle-water',
                'cleaning': 'fa-pump-soap',
                'vegetables': 'fa-carrot',
                'other': 'fa-box'
            };
            return icons[category] || 'fa-box';
        }

        function initAddToCart(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;

            if (product.unit === 'kg') {
                tempWeightProductId = id;
                document.getElementById('weight-product-name').textContent = product.name;
                document.getElementById('weight-input').value = '';
                openModal('weight-modal');
                setTimeout(() => document.getElementById('weight-input').focus(), 100);
            } else {
                addToCart(id, 1);
            }
        }

        function confirmWeight() {
            const weight = parseFloat(document.getElementById('weight-input').value);
            if (weight && weight > 0) {
                addToCart(tempWeightProductId, weight);
                closeModal('weight-modal');
            } else {
                alert('الرجاء إدخال وزن صحيح');
            }
        }

        function addToCart(id, quantity) {
            const product = products.find(p => p.id === id);
            const existingItem = cart.find(item => item.product_id === id);

            if (existingItem) {
                // If it's a piece, just add 1. If KG, update weight? 
                // For simplicity, usually POS adds separate line or increments piece.
                // Let's increment quantity/weight
                existingItem.quantity += quantity;
                existingItem.total = existingItem.quantity * existingItem.price;
            } else {
                cart.push({
                    product_id: id,
                    name: product.name,
                    price: product.price,
                    unit: product.unit,
                    quantity: quantity,
                    total: quantity * product.price
                });
            }
            renderCart();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            renderCart();
        }

        function renderCart() {
            const container = document.getElementById('cart-items');
            container.innerHTML = '';
            
            let total = 0;
            let count = 0;

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="h-full flex flex-col items-center justify-center text-slate-400 mt-10">
                        <i class="fa-solid fa-basket-shopping text-4xl mb-2"></i>
                        <p>السلة فارغة</p>
                    </div>`;
            } else {
                cart.forEach((item, index) => {
                    total += item.total;
                    count++; // Counting lines
                    
                    const div = document.createElement('div');
                    div.className = 'flex justify-between items-center bg-slate-50 p-2 rounded-lg border border-slate-100';
                    div.innerHTML = `
                        <div>
                            <p class="font-bold text-sm text-slate-800">${item.name}</p>
                            <p class="text-xs text-slate-500">
                                ${item.quantity.toFixed(item.unit === 'kg' ? 3 : 0)} 
                                ${item.unit === 'kg' ? 'كجم' : 'x'} 
                                × ${item.price} د.ل
                            </p>
                        </div>
                        <div class="flex items-center gap-3">
                            <span class="font-bold text-emerald-600">${item.total.toFixed(2)}</span>
                            <button onclick="removeFromCart(${index})" class="text-red-400 hover:text-red-600">
                                <i class="fa-solid fa-trash-can"></i>
                            </button>
                        </div>
                    `;
                    container.appendChild(div);
                });
            }

            document.getElementById('cart-total').textContent = total.toFixed(2);
            document.getElementById('cart-count').textContent = count;
        }

        function checkout() {
            if (cart.length === 0) {
                alert('السلة فارغة!');
                return;
            }

            const total = cart.reduce((sum, item) => sum + item.total, 0);
            const invoiceId = Date.now().toString().slice(-6);
            const date = new Date().toLocaleString('ar-LY');

            const sale = {
                id: invoiceId,
                date: date,
                items: [...cart],
                total: total
            };

            // Deduct stock (simplified)
            cart.forEach(cartItem => {
                const product = products.find(p => p.id === cartItem.product_id);
                if(product) {
                    product.stock -= cartItem.quantity;
                }
            });

            sales.unshift(sale); // Add to history
            saveData();
            
            // Show Receipt
            document.getElementById('receipt-id').textContent = invoiceId;
            document.getElementById('receipt-date').textContent = date;
            document.getElementById('receipt-total').textContent = total.toFixed(2) + ' د.ل';
            
            const receiptItems = document.getElementById('receipt-items');
            receiptItems.innerHTML = '';
            cart.forEach(item => {
                receiptItems.innerHTML += `
                    <div class="flex justify-between border-b border-dashed border-slate-200 py-1">
                        <span>${item.name} <span class="text-xs text-slate-400">(${item.quantity.toFixed(item.unit==='kg'?3:0)})</span></span>
                        <span>${item.total.toFixed(2)}</span>
                    </div>
                `;
            });

            openModal('receipt-modal');

            // Reset
            cart = [];
            renderCart();
            renderInventory(); // Update stock view
        }

        // --- Inventory Logic ---
        function renderInventory(search = '') {
            const tbody = document.getElementById('inventory-table-body');
            tbody.innerHTML = '';

            const filtered = products.filter(p => p.name.includes(search));

            filtered.forEach(p => {
                const tr = document.createElement('tr');
                tr.className = 'hover:bg-slate-50 transition-colors';
                
                // Expiry Logic
                const expiryDate = new Date(p.expiry);
                const today = new Date();
                const diffTime = expiryDate - today;
                const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24)); 
                
                let expiryClass = "text-slate-600";
                let expiryIcon = "";
                if (diffDays < 0) {
                    expiryClass = "text-red-600 font-bold";
                    expiryIcon = `<i class="fa-solid fa-triangle-exclamation ml-1"></i> منتهي`;
                } else if (diffDays < 30) {
                    expiryClass = "text-amber-600 font-bold";
                    expiryIcon = `<i class="fa-solid fa-clock ml-1"></i> ينتهي قريباً`;
                }

                tr.innerHTML = `
                    <td class="p-4 font-bold text-slate-700">${p.name}</td>
                    <td class="p-4 text-slate-500 text-sm">${getCategoryName(p.category)}</td>
                    <td class="p-4 text-slate-500 text-sm">${p.unit === 'kg' ? 'كجم' : 'قطعة'}</td>
                    <td class="p-4 font-bold text-emerald-600">${p.price.toFixed(2)} د.ل</td>
                    <td class="p-4 text-slate-700">${p.stock.toFixed(2)}</td>
                    <td class="p-4 text-sm ${expiryClass}">
                        ${p.expiry} <br> <span class="text-xs">${expiryIcon}</span>
                    </td>
                    <td class="p-4 text-center">
                        <button onclick="deleteProduct(${p.id})" class="text-red-500 hover:bg-red-50 p-2 rounded-lg transition-colors"><i class="fa-solid fa-trash"></i></button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        function getCategoryName(cat) {
            const map = {
                'food': 'مواد غذائية', 'drinks': 'مشروبات', 'cleaning': 'منظفات', 'vegetables': 'خضروات', 'other': 'أخرى'
            };
            return map[cat] || cat;
        }

        function handleProductSubmit(e) {
            e.preventDefault();
            const formData = new FormData(e.target);
            
            const newProduct = {
                id: Date.now(),
                name: formData.get('name'),
                price: parseFloat(formData.get('price')),
                unit: formData.get('unit'),
                category: formData.get('category'),
                stock: parseFloat(formData.get('stock')),
                expiry: formData.get('expiry') // Storing as YYYY-MM-DD string
            };

            products.push(newProduct);
            saveData();
            renderInventory();
            renderProducts(); // Update POS grid
            closeModal('add-product-modal');
            e.target.reset();
        }

        function deleteProduct(id) {
            if(confirm('هل أنت متأكد من حذف هذا المنتج؟')) {
                products = products.filter(p => p.id !== id);
                saveData();
                renderInventory();
                renderProducts();
            }
        }

        // --- Sales History ---
        function renderSalesHistory() {
            const tbody = document.getElementById('sales-table-body');
            tbody.innerHTML = '';
            
            sales.forEach(sale => {
                const tr = document.createElement('tr');
                tr.className = 'hover:bg-slate-50';
                tr.innerHTML = `
                    <td class="p-4 font-mono text-slate-500">#${sale.id}</td>
                    <td class="p-4 text-slate-700 text-sm">${sale.date}</td>
                    <td class="p-4 text-slate-700 text-sm">${sale.items.length}</td>
                    <td class="p-4 font-bold text-emerald-600">${sale.total.toFixed(2)} د.ل</td>
                    <td class="p-4 text-center">
                        <button class="text-blue-500 hover:text-blue-700 text-sm">عرض</button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        // --- Dashboard ---
        function updateDashboard() {
            // Total Sales
            const totalSales = sales.reduce((sum, sale) => sum + sale.total, 0);
            document.getElementById('dash-total-sales').textContent = totalSales.toFixed(2) + ' د.ل';
            
            // Counts
            document.getElementById('dash-invoice-count').textContent = sales.length;
            document.getElementById('dash-product-count').textContent = products.length;

            // Expiry
            const today = new Date();
            const expiryCount = products.filter(p => {
                const expDate = new Date(p.expiry);
                const diffTime = expDate - today;
                const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
                return diffDays < 30; // Less than 30 days
            }).length;
            document.getElementById('dash-expiry-count').textContent = expiryCount;

            // Recent Sales
            const recentContainer = document.getElementById('dash-recent-sales');
            recentContainer.innerHTML = '';
            sales.slice(0, 5).forEach(sale => {
                const div = document.createElement('div');
                div.className = 'flex justify-between items-center p-3 bg-slate-50 rounded-lg border border-slate-100';
                div.innerHTML = `
                    <div>
                        <span class="font-bold text-slate-700">فاتورة #${sale.id}</span>
                        <span class="text-xs text-slate-400 block">${sale.date}</span>
                    </div>
                    <span class="font-bold text-emerald-600">${sale.total.toFixed(2)} د.ل</span>
                `;
                recentContainer.appendChild(div);
            });
        }

        // --- Helpers ---
        function openModal(id) {
            document.getElementById(id).classList.remove('hidden');
            setTimeout(() => {
                const content = document.querySelector(`#${id} > div`);
                content.classList.remove('scale-95', 'opacity-0');
                content.classList.add('scale-100', 'opacity-100');
            }, 10);
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        function printReceipt() {
            window.print();
        }

        // Close modal on click outside
        window.onclick = function(event) {
            if (event.target.classList.contains('fixed')) {
                event.target.classList.add('hidden');
            }
        }
    </script>
</body>
</html>
