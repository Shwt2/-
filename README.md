<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منظومة مبيعات مكتبة الشروق - الإصدار 2026 Pro</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            direction: rtl;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #1a1a1a;
            font-size: 12px;
            min-height: 100vh;
        }

        /* Modern Delphi Style */
        .modern-form {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border: 1px solid #dee2e6;
            border-radius: 6px;
            padding: 2px;
            margin: 5px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .modern-panel {
            background: #fff;
            border: 1px solid #dee2e6;
            border-radius: 6px;
            padding: 8px;
            margin: 6px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .modern-button {
            background: linear-gradient(180deg, #0d6efd 0%, #0956ca 100%);
            border: 1px solid #0d6efd;
            border-radius: 5px;
            padding: 8px 16px;
            font-family: 'Segoe UI', sans-serif;
            font-size: 12px;
            font-weight: 500;
            cursor: pointer;
            color: #fff;
            text-align: center;
            margin: 4px;
            transition: all 0.2s;
            box-shadow: 0 2px 4px rgba(13, 110, 253, 0.2);
        }

        .modern-button:hover {
            background: linear-gradient(180deg, #0860ca 0%, #074399 100%);
            box-shadow: 0 4px 8px rgba(13, 110, 253, 0.3);
            transform: translateY(-1px);
        }

        .modern-button:active {
            transform: translateY(0);
            box-shadow: 0 1px 2px rgba(13, 110, 253, 0.2);
        }

        .modern-input {
            background-color: #fff;
            border: 1px solid #dee2e6;
            border-radius: 4px;
            padding: 8px 12px;
            font-family: 'Segoe UI', sans-serif;
            font-size: 12px;
            color: #495057;
            margin: 4px 0;
            transition: border-color 0.2s;
        }

        .modern-input:focus {
            outline: none;
            border-color: #0d6efd;
            box-shadow: 0 0 0 3px rgba(13, 110, 253, 0.1);
        }

        .modern-select {
            background-color: #fff;
            border: 1px solid #dee2e6;
            border-radius: 4px;
            padding: 8px 12px;
            font-family: 'Segoe UI', sans-serif;
            font-size: 12px;
            color: #495057;
            margin: 4px 0;
            cursor: pointer;
            transition: border-color 0.2s;
        }

        .modern-select:focus {
            outline: none;
            border-color: #0d6efd;
            box-shadow: 0 0 0 3px rgba(13, 110, 253, 0.1);
        }

        .modern-label {
            background-color: transparent;
            font-size: 12px;
            padding: 4px;
            color: #495057;
            font-weight: 500;
        }

        .modern-groupbox {
            background: #fff;
            border: 1px solid #dee2e6;
            border-radius: 6px;
            padding: 12px;
            margin: 8px;
            position: relative;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .modern-groupbox-title {
            position: absolute;
            top: -10px;
            right: 12px;
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 0 8px;
            font-weight: 600;
            font-size: 12px;
            color: #0d6efd;
        }

        .modern-grid {
            border: 1px solid #dee2e6;
            background-color: #fff;
            width: 100%;
            border-collapse: collapse;
            font-size: 12px;
            margin: 6px 0;
            border-radius: 4px;
            overflow: hidden;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .modern-grid th {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border: 1px solid #dee2e6;
            padding: 8px;
            text-align: right;
            font-weight: 600;
            color: #0d6efd;
        }

        .modern-grid td {
            border: 1px solid #e9ecef;
            padding: 8px;
            text-align: right;
        }

        .modern-grid tr:hover {
            background-color: #f8f9fa;
        }

        .modern-window {
            background: #fff;
            border: 1px solid #dee2e6;
            border-radius: 8px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.15);
            position: fixed;
            z-index: 1000;
            min-width: 400px;
            max-width: 90vw;
            max-height: 90vh;
            display: none;
        }

        .modern-window.show {
            display: block;
        }

        .modern-window-caption {
            background: linear-gradient(90deg, #0d6efd 0%, #0860ca 100%);
            color: #fff;
            padding: 12px;
            font-weight: 600;
            font-size: 13px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            user-select: none;
            cursor: move;
            border-radius: 8px 8px 0 0;
        }

        .modern-window-close {
            width: 28px;
            height: 28px;
            background: rgba(255,255,255,0.2);
            border: none;
            border-radius: 4px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 16px;
            color: #fff;
            transition: all 0.2s;
        }

        .modern-window-close:hover {
            background: rgba(255,255,255,0.3);
        }

        .modern-window-content {
            padding: 12px;
            overflow-y: auto;
            max-height: calc(90vh - 50px);
        }

        .modern-statusbar {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border-top: 1px solid #dee2e6;
            padding: 8px;
            display: flex;
            font-size: 11px;
            position: fixed;
            bottom: 0;
            width: 100%;
            height: 24px;
            align-items: center;
            box-shadow: 0 -2px 8px rgba(0,0,0,0.05);
        }

        .modern-statusbar-panel {
            padding: 4px 8px;
            border-right: 1px solid #dee2e6;
            flex: 1;
            color: #495057;
        }

        /* Main Layout */
        .main-container {
            display: flex;
            height: 100vh;
            flex-direction: column;
        }

        .menu-bar {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border-bottom: 1px solid #dee2e6;
            padding: 6px;
            display: flex;
            gap: 0;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        .menu-item {
            padding: 6px 12px;
            cursor: pointer;
            user-select: none;
            position: relative;
            color: #495057;
            font-weight: 500;
            border-radius: 4px;
            transition: all 0.2s;
        }

        .menu-item:hover {
            background: #0d6efd;
            color: #fff;
        }

        .submenu {
            position: absolute;
            background: #fff;
            border: 1px solid #dee2e6;
            border-radius: 6px;
            display: none;
            min-width: 160px;
            top: 100%;
            right: 0;
            z-index: 100;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            margin-top: 4px;
        }

        .submenu.show {
            display: block;
        }

        .submenu-item {
            padding: 8px 16px;
            cursor: pointer;
            user-select: none;
            border-bottom: 1px solid #f0f0f0;
            color: #495057;
            transition: all 0.2s;
        }

        .submenu-item:last-child {
            border-bottom: none;
        }

        .submenu-item:hover {
            background: #f8f9fa;
            color: #0d6efd;
            padding-right: 20px;
        }

        .content-area {
            flex: 1;
            overflow: auto;
            margin-bottom: 24px;
            padding: 10px;
        }

        .form-row {
            display: flex;
            gap: 12px;
            margin: 6px 0;
            align-items: center;
        }

        .form-label {
            width: 140px;
            text-align: right;
            font-weight: 500;
            color: #495057;
        }

        .form-control {
            flex: 1;
            min-width: 200px;
        }

        .button-group {
            display: flex;
            gap: 8px;
            margin: 8px 0;
            justify-content: center;
            flex-wrap: wrap;
        }

        .toolbar {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border-bottom: 1px solid #dee2e6;
            padding: 8px;
            display: flex;
            gap: 8px;
            align-items: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            flex-wrap: wrap;
        }

        .toolbar-separator {
            width: 1px;
            height: 22px;
            background-color: #dee2e6;
            margin: 0 4px;
        }

        .input-group {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin: 8px;
        }

        .message-box {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: #fff;
            border: 1px solid #dee2e6;
            border-radius: 8px;
            padding: 0;
            z-index: 2000;
            min-width: 300px;
            max-width: 500px;
            display: none;
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
        }

        .message-box.show {
            display: block;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translate(-50%, -50%) scale(0.9);
            }
            to {
                opacity: 1;
                transform: translate(-50%, -50%) scale(1);
            }
        }

        .message-box-title {
            background: linear-gradient(90deg, #0d6efd 0%, #0860ca 100%);
            color: #fff;
            padding: 12px;
            font-weight: 600;
            border-radius: 8px 8px 0 0;
        }

        .message-box-content {
            padding: 16px;
            text-align: center;
            margin-bottom: 8px;
            color: #495057;
        }

        .message-box-buttons {
            display: flex;
            gap: 8px;
            justify-content: center;
            padding: 8px 16px 16px;
        }

        /* Specific Styles */
        .scanner-input-area {
            background-color: #fff;
            border: 1px solid #dee2e6;
            border-radius: 6px;
            padding: 12px;
            margin: 8px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .invoice-summary {
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            border: 1px solid #dee2e6;
            border-radius: 6px;
            padding: 12px;
            margin: 8px;
        }

        .summary-row {
            display: flex;
            justify-content: space-between;
            padding: 6px;
            border-bottom: 1px solid #dee2e6;
            color: #495057;
        }

        .summary-row.total {
            font-weight: 600;
            border: 2px solid #0d6efd;
            border-radius: 4px;
            padding: 8px;
            margin: 4px 0;
            background: #fff;
            color: #0d6efd;
        }

        .hidden {
            display: none !important;
        }

        /* Keyboard shortcut hint */
        .shortcut-hint {
            font-size: 10px;
            color: #868e96;
            margin-top: 2px;
        }

        /* Success/Error colors */
        .success { color: #198754; }
        .error { color: #dc3545; }
        .warning { color: #ffc107; }
        .info { color: #0d6efd; }
    </style>
</head>
<body>
    <div class="main-container">
        <!-- Menu Bar -->
        <div class="menu-bar">
            <div class="menu-item">
                ملف
                <div class="submenu">
                    <div class="submenu-item" onclick="newInvoice()" title="F1">فاتورة جديدة <span class="shortcut-hint">(F1)</span></div>
                    <div class="submenu-item" onclick="openFile()" title="F2">فتح ملف <span class="shortcut-hint">(F2)</span></div>
                    <div class="submenu-item" onclick="saveFile()" title="F3">حفظ <span class="shortcut-hint">(F3)</span></div>
                    <div class="submenu-item" onclick="exportBackup()">نسخة احتياطية</div>
                    <div class="submenu-item" onclick="importBackup()">استيراد</div>
                    <div class="submenu-item" style="border-top: 1px solid #dee2e6; margin-top: 4px;" onclick="exitApp()">خروج</div>
                </div>
            </div>
            <div class="menu-item">
                تحرير
                <div class="submenu">
                    <div class="submenu-item" onclick="undo()">تراجع</div>
                    <div class="submenu-item" onclick="redo()">إعادة</div>
                </div>
            </div>
            <div class="menu-item">
                بيانات
                <div class="submenu">
                    <div class="submenu-item" onclick="showProductsForm()" title="F4">بطاقة الصنف <span class="shortcut-hint">(F4)</span></div>
                    <div class="submenu-item" onclick="showCustomersForm()" title="F5">بطاقة العميل <span class="shortcut-hint">(F5)</span></div>
                    <div class="submenu-item" onclick="showEmployeesForm()" title="F6">بطاقة الموظف <span class="shortcut-hint">(F6)</span></div>
                    <div class="submenu-item" onclick="showSuppliersForm()">بطاقة المورد</div>
                </div>
            </div>
            <div class="menu-item">
                عمليات
                <div class="submenu">
                    <div class="submenu-item" onclick="showPointOfSale()" title="F7">نقطة البيع <span class="shortcut-hint">(F7)</span></div>
                    <div class="submenu-item" onclick="showReturns()" title="F8">نقطة الترجيع <span class="shortcut-hint">(F8)</span></div>
                    <div class="submenu-item" onclick="showWholesale()" title="F9">البيع بالجملة <span class="shortcut-hint">(F9)</span></div>
                    <div class="submenu-item" onclick="showPurchases()">المشتريات والوارد</div>
                    <div class="submenu-item" onclick="showExpenses()">المصروفات</div>
                </div>
            </div>
            <div class="menu-item">
                تقارير
                <div class="submenu">
                    <div class="submenu-item" onclick="showSalesReport()" title="F10">تقرير المبيعات <span class="shortcut-hint">(F10)</span></div>
                    <div class="submenu-item" onclick="showGeneralReport()">التقرير العام</div>
                    <div class="submenu-item" onclick="showInventoryReport()">تقرير المخزون</div>
                    <div class="submenu-item" onclick="showExpensesReport()">تقرير المصروفات</div>
                </div>
            </div>
            <div class="menu-item">
                إعدادات
                <div class="submenu">
                    <div class="submenu-item" onclick="showSettings()" title="F11">الإعدادات <span class="shortcut-hint">(F11)</span></div>
                    <div class="submenu-item" onclick="showUsersForm()" title="F12">إدارة المستخدمين <span class="shortcut-hint">(F12)</span></div>
                    <div class="submenu-item" onclick="showAbout()">عن البرنامج</div>
                </div>
            </div>
        </div>

        <!-- Toolbar -->
        <div class="toolbar">
            <button class="modern-button" title="فاتورة جديدة (F1)" onclick="newInvoice()">📄 جديد</button>
            <button class="modern-button" title="حفظ (F3)" onclick="saveFile()">💾 حفظ</button>
            <button class="modern-button" title="فتح (F2)" onclick="openFile()">📂 فتح</button>
            <div class="toolbar-separator"></div>
            <button class="modern-button" title="نقطة البيع (F7)" onclick="showPointOfSale()">🛒 بيع</button>
            <button class="modern-button" title="ترجيع (F8)" onclick="showReturns()">↩️ ترجيع</button>
            <button class="modern-button" title="جملة (F9)" onclick="showWholesale()">📦 جملة</button>
            <div class="toolbar-separator"></div>
            <button class="modern-button" title="تقارير (F10)" onclick="showGeneralReport()">📊 تقارير</button>
            <button class="modern-button" title="إعدادات (F11)" onclick="showSettings()">⚙️ إعدادات</button>
        </div>

        <!-- Content Area -->
        <div class="content-area" id="contentArea">
            <!-- Point of Sale Form -->
            <div id="posForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">🛒 نقطة البيع</div>
                    
                    <div class="modern-groupbox" style="margin-top: 20px;">
                        <div class="modern-groupbox-title">إدخال المنتجات</div>
                        <div class="scanner-input-area">
                            <div class="form-row">
                                <label class="form-label">كود الصنف/الماسح:</label>
                                <input type="text" id="scannerInput" class="modern-input form-control" placeholder="امسح الكود هنا..." autofocus>
                            </div>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">بنود الفاتورة</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="invoiceGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 25%;">الصنف</th>
                                        <th style="width: 15%;">الكود</th>
                                        <th style="width: 12%;">الكمية</th>
                                        <th style="width: 12%;">السعر</th>
                                        <th style="width: 15%;">المجموع</th>
                                        <th style="width: 10%;">الإجراءات</th>
                                        <th style="width: 11%;">تعديل</th>
                                    </tr>
                                </thead>
                                <tbody id="invoiceBody">
                                    <tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد منتجات</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>

                    <div style="display: flex; gap: 12px; margin: 12px;">
                        <!-- Left Side - Summary -->
                        <div style="flex: 1;">
                            <div class="invoice-summary">
                                <div style="font-weight: 600; margin-bottom: 8px; text-align: center; color: #0d6efd;">ملخص الفاتورة</div>
                                <div class="summary-row">
                                    <span>عدد البنود:</span>
                                    <span id="itemCount" style="font-weight: 600;">0</span>
                                </div>
                                <div class="summary-row">
                                    <span>الإجمالي قبل الضريبة:</span>
                                    <span id="subtotal" style="font-weight: 600;">0.00</span>
                                </div>
                                <div class="summary-row">
                                    <span>الضريبة (15%):</span>
                                    <span id="taxAmount" style="font-weight: 600;">0.00</span>
                                </div>
                                <div class="summary-row total">
                                    <span>الإجمالي النهائي:</span>
                                    <span id="totalAmount" style="color: #dc3545;">0.00</span>
                                </div>
                            </div>
                        </div>

                        <!-- Right Side - Payment -->
                        <div style="flex: 1;">
                            <div class="modern-groupbox">
                                <div class="modern-groupbox-title">طريقة الدفع</div>
                                <div class="form-row">
                                    <label class="form-label">طريقة الدفع:</label>
                                    <select id="paymentMethod" class="modern-select form-control">
                                        <option value="cash">💵 نقداً</option>
                                        <option value="card">💳 بطاقة ائتمان</option>
                                        <option value="check">✓ شيك</option>
                                        <option value="credit">📋 على الحساب</option>
                                    </select>
                                </div>
                                <div class="form-row">
                                    <label class="form-label">اسم العميل:</label>
                                    <input type="text" id="customerName" class="modern-input form-control" placeholder="اختياري">
                                </div>
                                <div class="form-row">
                                    <label class="form-label">الملاحظات:</label>
                                    <textarea id="invoiceNotes" class="modern-input form-control" style="height: 50px; resize: vertical;"></textarea>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Buttons -->
                    <div class="modern-groupbox">
                        <div class="button-group" style="justify-content: flex-start;">
                            <button class="modern-button" style="min-width: 120px;" onclick="completeInvoice()">✅ إتمام الفاتورة</button>
                            <button class="modern-button" style="min-width: 120px;" onclick="togglePendingInvoices()">⏱️ فواتير معلقة</button>
                            <button class="modern-button" style="min-width: 100px;" onclick="printInvoice()">🖨️ طباعة</button>
                            <button class="modern-button" style="min-width: 100px;" onclick="clearInvoice()">🗑️ مسح</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Products Form -->
            <div id="productsForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">📦 بطاقة الصنف</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إضافة صنف جديد</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">كود الصنف:</div>
                                <input type="text" id="productCode" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">اسم الصنف:</div>
                                <input type="text" id="productName" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الفئة:</div>
                                <select id="productCategory" class="modern-select" style="width: 100%;">
                                    <option>اختر الفئة</option>
                                    <option>أقلام</option>
                                    <option>دفاتر</option>
                                    <option>أوراق</option>
                                    <option>أدوات رسم</option>
                                    <option>أخرى</option>
                                </select>
                            </div>
                            <div>
                                <div class="modern-label">السعر:</div>
                                <input type="number" id="productPrice" class="modern-input" step="0.01" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الكمية:</div>
                                <input type="number" id="productQuantity" class="modern-input" min="0" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">المورد:</div>
                                <input type="text" id="productSupplier" class="modern-input" style="width: 100%;">
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addProduct()">➕ إضافة</button>
                            <button class="modern-button" onclick="updateProduct()">✏️ تحديث</button>
                            <button class="modern-button" onclick="clearProductForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">قائمة الأصناف</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="productsGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 15%;">الكود</th>
                                        <th style="width: 25%;">الاسم</th>
                                        <th style="width: 15%;">الفئة</th>
                                        <th style="width: 12%;">السعر</th>
                                        <th style="width: 10%;">المخزون</th>
                                        <th style="width: 15%;">المورد</th>
                                        <th style="width: 8%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="productsBody">
                                    <tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد منتجات</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Customers Form -->
            <div id="customersForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">👥 بطاقة العميل</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إضافة عميل جديد</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">رقم العميل:</div>
                                <input type="text" id="customerCode" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">اسم العميل:</div>
                                <input type="text" id="customerNameInput" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">النوع:</div>
                                <select id="customerType" class="modern-select" style="width: 100%;">
                                    <option value="retail">تجزئة</option>
                                    <option value="wholesale">جملة</option>
                                    <option value="corporate">شركة</option>
                                </select>
                            </div>
                            <div>
                                <div class="modern-label">الهاتف:</div>
                                <input type="tel" id="customerPhone" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">البريد:</div>
                                <input type="email" id="customerEmail" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">العنوان:</div>
                                <input type="text" id="customerAddress" class="modern-input" style="width: 100%;">
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addCustomer()">➕ إضافة</button>
                            <button class="modern-button" onclick="clearCustomerForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">قائمة العملاء</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="customersGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 15%;">الرقم</th>
                                        <th style="width: 25%;">الاسم</th>
                                        <th style="width: 15%;">النوع</th>
                                        <th style="width: 15%;">الهاتف</th>
                                        <th style="width: 15%;">الرصيد</th>
                                        <th style="width: 10%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="customersBody">
                                    <tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد عملاء</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Employees Form -->
            <div id="employeesForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">👔 بطاقة الموظف</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إضافة موظف جديد</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">رقم الموظف:</div>
                                <input type="text" id="employeeCode" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">اسم الموظف:</div>
                                <input type="text" id="employeeName" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">المنصب:</div>
                                <input type="text" id="employeePosition" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الراتب:</div>
                                <input type="number" id="employeeSalary" class="modern-input" step="0.01" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الهاتف:</div>
                                <input type="tel" id="employeePhone" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">تاريخ التعيين:</div>
                                <input type="date" id="employeeStartDate" class="modern-input" style="width: 100%;">
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addEmployee()">➕ إضافة</button>
                            <button class="modern-button" onclick="clearEmployeeForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">قائمة الموظفين</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="employeesGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 15%;">الرقم</th>
                                        <th style="width: 25%;">الاسم</th>
                                        <th style="width: 15%;">المنصب</th>
                                        <th style="width: 12%;">الراتب</th>
                                        <th style="width: 18%;">التعيين</th>
                                        <th style="width: 10%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="employeesBody">
                                    <tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد موظفين</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Returns Form -->
            <div id="returnsForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">↩️ نقطة الترجيع</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إضافة ترجيع</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">رقم الفاتورة:</div>
                                <input type="text" id="returnCode" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الصنف:</div>
                                <input type="text" id="returnProduct" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الكمية:</div>
                                <input type="number" id="returnQuantity" class="modern-input" min="1" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">السبب:</div>
                                <textarea id="returnReason" class="modern-input" style="width: 100%; height: 50px;"></textarea>
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addReturn()">➕ إضافة</button>
                            <button class="modern-button" onclick="clearReturnForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">سجل الترجيعات</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="returnsGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 15%;">رقم الفاتورة</th>
                                        <th style="width: 25%;">الصنف</th>
                                        <th style="width: 10%;">الكمية</th>
                                        <th style="width: 25%;">السبب</th>
                                        <th style="width: 15%;">التاريخ</th>
                                        <th style="width: 10%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="returnsBody">
                                    <tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد ترجيعات</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Wholesale Form -->
            <div id="wholesaleForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">📦 البيع بالجملة</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إنشاء طلب جملة</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">اسم العميل:</div>
                                <input type="text" id="wholesaleCustomer" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الصنف:</div>
                                <input type="text" id="wholesaleProduct" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الكمية:</div>
                                <input type="number" id="wholesaleQuantity" class="modern-input" min="1" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الخصم (%):</div>
                                <input type="number" id="wholesaleDiscount" class="modern-input" min="0" max="100" style="width: 100%;">
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addWholesale()">➕ إنشاء</button>
                            <button class="modern-button" onclick="clearWholesaleForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">طلبات الجملة</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="wholesaleGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 20%;">العميل</th>
                                        <th style="width: 25%;">الصنف</th>
                                        <th style="width: 10%;">الكمية</th>
                                        <th style="width: 10%;">الخصم</th>
                                        <th style="width: 15%;">الإجمالي</th>
                                        <th style="width: 12%;">التاريخ</th>
                                        <th style="width: 8%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="wholesaleBody">
                                    <tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد طلبات</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Reports Form -->
            <div id="reportsForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">📊 التقارير</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">التقرير العام</div>
                        <div style="display: flex; gap: 16px; margin: 8px 0;">
                            <div style="flex: 1; background: linear-gradient(135deg, #e7f3ff 0%, #fff 100%); border: 1px solid #dee2e6; border-radius: 6px; padding: 12px; text-align: center;">
                                <div style="font-weight: 600; font-size: 12px; color: #0d6efd;">إجمالي المبيعات</div>
                                <div style="font-size: 20px; font-weight: 700; color: #0d6efd; margin-top: 6px;" id="totalSales">0.00</div>
                            </div>
                            <div style="flex: 1; background: linear-gradient(135deg, #fff3e0 0%, #fff 100%); border: 1px solid #dee2e6; border-radius: 6px; padding: 12px; text-align: center;">
                                <div style="font-weight: 600; font-size: 12px; color: #fd7e14;">إجمالي المصروفات</div>
                                <div style="font-size: 20px; font-weight: 700; color: #fd7e14; margin-top: 6px;" id="totalExpenses">0.00</div>
                            </div>
                            <div style="flex: 1; background: linear-gradient(135deg, #e8f5e9 0%, #fff 100%); border: 1px solid #dee2e6; border-radius: 6px; padding: 12px; text-align: center;">
                                <div style="font-weight: 600; font-size: 12px; color: #198754;">صافي الربح</div>
                                <div style="font-size: 20px; font-weight: 700; color: #198754; margin-top: 6px;" id="netProfit">0.00</div>
                            </div>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">كشف المبيعات</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="salesReportGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 15%;">رقم الفاتورة</th>
                                        <th style="width: 20%;">العميل</th>
                                        <th style="width: 12%;">المبلغ</th>
                                        <th style="width: 10%;">الضريبة</th>
                                        <th style="width: 12%;">الإجمالي</th>
                                        <th style="width: 12%;">طريقة الدفع</th>
                                        <th style="width: 12%;">التاريخ</th>
                                    </tr>
                                </thead>
                                <tbody id="salesReportBody">
                                    <tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد مبيعات</td></tr>
                                </tbody>
                            </table>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="printReport()">🖨️ طباعة</button>
                            <button class="modern-button" onclick="exportReport()">💾 تصدير</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Settings Form -->
            <div id="settingsForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">⚙️ الإعدادات</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">بيانات الشركة</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">اسم الشركة:</div>
                                <input type="text" id="companyName" class="modern-input" style="width: 100%;" value="مكتبة الشروق">
                            </div>
                            <div>
                                <div class="modern-label">رقم الهاتف:</div>
                                <input type="tel" id="companyPhone" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">البريد الإلكتروني:</div>
                                <input type="email" id="companyEmail" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">العنوان:</div>
                                <textarea id="companyAddress" class="modern-input" style="width: 100%; height: 50px;"></textarea>
                            </div>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">خيارات النظام</div>
                        <div class="form-row">
                            <label class="form-label">نسبة الضريبة (%):</label>
                            <input type="number" id="taxRate" class="modern-input form-control" value="15" min="0" max="100" step="0.1" style="width: 100px;">
                        </div>
                        <div class="form-row">
                            <label class="form-label">العملة:</label>
                            <select id="currency" class="modern-select form-control">
                                <option value="ريال">ريال سعودي (﷼)</option>
                                <option value="دولار">دولار أمريكي ($)</option>
                                <option value="يورو">يورو (€)</option>
                                <option value="درهم">درهم إماراتي (د.إ)</option>
                            </select>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">النسخ الاحتياطية</div>
                        <div class="button-group" style="justify-content: flex-start;">
                            <button class="modern-button" onclick="exportBackup()">💾 تصدير النسخة</button>
                            <button class="modern-button" onclick="importBackup()">📂 استيراد النسخة</button>
                            <button class="modern-button" onclick="clearAllData()">🗑️ مسح جميع البيانات</button>
                        </div>
                    </div>

                    <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                        <button class="modern-button" onclick="saveSettings()">💾 حفظ الإعدادات</button>
                    </div>
                </div>
            </div>

            <!-- Users Form -->
            <div id="usersForm" class="modern-form hidden">
                <div style="padding: 6px;">
                    <div style="font-weight: 600; margin-bottom: 12px; font-size: 14px; color: #0d6efd;">🔐 إدارة المستخدمين</div>
                    
                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">إضافة مستخدم جديد</div>
                        <div class="input-group">
                            <div>
                                <div class="modern-label">اسم المستخدم:</div>
                                <input type="text" id="userName" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">كلمة المرور:</div>
                                <input type="password" id="userPassword" class="modern-input" style="width: 100%;">
                            </div>
                            <div>
                                <div class="modern-label">الصلاحية:</div>
                                <select id="userRole" class="modern-select" style="width: 100%;">
                                    <option value="admin">مدير</option>
                                    <option value="cashier">أمين صندوق</option>
                                    <option value="manager">مدير مستخدمين</option>
                                    <option value="viewer">عارض فقط</option>
                                </select>
                            </div>
                            <div>
                                <div class="modern-label">البريد الإلكتروني:</div>
                                <input type="email" id="userEmail" class="modern-input" style="width: 100%;">
                            </div>
                        </div>
                        <div class="button-group" style="justify-content: flex-start; margin-top: 12px;">
                            <button class="modern-button" onclick="addUser()">➕ إضافة</button>
                            <button class="modern-button" onclick="clearUserForm()">🗑️ مسح</button>
                        </div>
                    </div>

                    <div class="modern-groupbox">
                        <div class="modern-groupbox-title">قائمة المستخدمين</div>
                        <div style="overflow-x: auto;">
                            <table class="modern-grid" id="usersGrid">
                                <thead>
                                    <tr>
                                        <th style="width: 25%;">اسم المستخدم</th>
                                        <th style="width: 25%;">البريد</th>
                                        <th style="width: 25%;">الصلاحية</th>
                                        <th style="width: 25%;">حذف</th>
                                    </tr>
                                </thead>
                                <tbody id="usersBody">
                                    <tr><td colspan="4" style="text-align: center; padding: 8px;">لا توجد مستخدمين</td></tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Default Welcome Screen -->
            <div id="welcomeForm" class="modern-form" style="display: flex; align-items: center; justify-content: center; height: 100%;">
                <div style="text-align: center; background: linear-gradient(135deg, #e7f3ff 0%, #fff 100%); border: 2px solid #0d6efd; border-radius: 8px; padding: 40px; min-width: 450px; box-shadow: 0 10px 40px rgba(13, 110, 253, 0.2);">
                    <div style="font-size: 36px; font-weight: 700; margin-bottom: 20px; color: #0d6efd;">📚 مكتبة الشروق</div>
                    <div style="font-size: 18px; margin-bottom: 30px; color: #495057;">منظومة مبيعات متكاملة احترافية</div>
                    <div style="background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%); border: 2px solid #0d6efd; border-radius: 8px; padding: 24px; margin-bottom: 24px;">
                        <div style="font-weight: 700; margin-bottom: 12px; color: #0d6efd; font-size: 16px;">الإصدار 2026 Pro</div>
                        <div style="font-size: 13px; color: #495057; line-height: 1.6;">نظام متكامل لإدارة المبيعات والمخزون والتقارير<br>الإصدار الأحدث والأكثر احترافية</div>
                        <div style="font-size: 12px; color: #868e96; margin-top: 12px;">© 2026 جميع الحقوق محفوظة لمكتبة الشروق</div>
                    </div>
                    <div style="font-size: 13px; color: #495057; margin-top: 20px; background: #fff3e0; padding: 12px; border-radius: 6px; border-right: 4px solid #fd7e14;">
                        💡 استخدم الاختصارات: F1-F12 للوصول السريع للأقسام المختلفة
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Status Bar -->
    <div class="modern-statusbar">
        <div class="modern-statusbar-panel">جاهز</div>
        <div class="modern-statusbar-panel" style="flex: 0;" id="statusTime">00:00:00</div>
    </div>

    <!-- Modals -->
    <!-- Edit Item Modal -->
    <div id="editItemModal" class="modern-window">
        <div class="modern-window-caption">
            <span>تعديل البند</span>
            <button class="modern-window-close" onclick="closeEditItemModal()">✕</button>
        </div>
        <div class="modern-window-content">
            <div class="form-row">
                <label class="form-label">السعر الجديد:</label>
                <input type="number" id="editPrice" class="modern-input form-control" step="0.01">
            </div>
            <div class="form-row">
                <label class="form-label">الكمية الجديدة:</label>
                <input type="number" id="editQuantity" class="modern-input form-control" min="1">
            </div>
            <div class="button-group" style="justify-content: flex-start;">
                <button class="modern-button" onclick="saveItemEdit()">✅ حفظ</button>
                <button class="modern-button" style="background: #6c757d; border-color: #6c757d;" onclick="closeEditItemModal()">❌ إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Pending Invoices Modal -->
    <div id="pendingInvoicesModal" class="modern-window" style="min-width: 500px;">
        <div class="modern-window-caption">
            <span>⏱️ الفواتير المعلقة</span>
            <button class="modern-window-close" onclick="closePendingInvoicesModal()">✕</button>
        </div>
        <div class="modern-window-content" style="overflow-y: auto; max-height: 400px;">
            <div id="pendingInvoicesList" style="padding: 8px;"></div>
        </div>
        <div style="padding: 8px; text-align: center; border-top: 1px solid #dee2e6;">
            <button class="modern-button" onclick="closePendingInvoicesModal()">إغلاق</button>
        </div>
    </div>

    <!-- Message Box -->
    <div id="messageBox" class="message-box">
        <div class="message-box-title" id="messageTitle">معلومة</div>
        <div class="message-box-content" id="messageContent"></div>
        <div class="message-box-buttons">
            <button class="modern-button" onclick="closeMessageBox()">موافق</button>
        </div>
    </div>

    <!-- Hidden file input -->
    <input type="file" id="importFileInput" class="hidden" accept=".json" onchange="importBackupFile(event)">

    <script>
        // Global Data Store
        let appData = {
            products: [],
            customers: [],
            employees: [],
            sales: [],
            returns: [],
            wholesale: [],
            expenses: [],
            assets: [],
            bankTransactions: [],
            imports: [],
            users: [],
            invoices: [],
            purchases: []
        };

        let currentInvoice = {
            id: null,
            number: '',
            items: [],
            customer: '',
            paymentMethod: 'cash',
            notes: '',
            date: new Date().toLocaleDateString('ar-SA'),
            time: new Date().toLocaleTimeString('ar-SA'),
            subtotal: 0,
            tax: 0,
            total: 0,
            status: 'draft'
        };

        let editingProductId = null;
        let editingItemIndex = null;

        // Keyboard Shortcuts
        document.addEventListener('keydown', function(e) {
            if (e.key === 'F1') { e.preventDefault(); newInvoice(); }
            if (e.key === 'F2') { e.preventDefault(); openFile(); }
            if (e.key === 'F3') { e.preventDefault(); saveFile(); }
            if (e.key === 'F4') { e.preventDefault(); showProductsForm(); }
            if (e.key === 'F5') { e.preventDefault(); showCustomersForm(); }
            if (e.key === 'F6') { e.preventDefault(); showEmployeesForm(); }
            if (e.key === 'F7') { e.preventDefault(); showPointOfSale(); }
            if (e.key === 'F8') { e.preventDefault(); showReturns(); }
            if (e.key === 'F9') { e.preventDefault(); showWholesale(); }
            if (e.key === 'F10') { e.preventDefault(); showGeneralReport(); }
            if (e.key === 'F11') { e.preventDefault(); showSettings(); }
            if (e.key === 'F12') { e.preventDefault(); showUsersForm(); }
        });

        // Initialize
        window.addEventListener('load', function() {
            loadFromStorage();
            setupMenus();
            setupScannerInput();
            updateStatusBar();
            setInterval(updateStatusBar, 1000);
            displayAllLists();
            showPointOfSale();
        });

        // Menu Setup
        function setupMenus() {
            document.querySelectorAll('.menu-item').forEach(item => {
                item.addEventListener('click', function(e) {
                    const submenu = this.querySelector('.submenu');
                    if (submenu) {
                        e.preventDefault();
                        document.querySelectorAll('.submenu').forEach(s => s.classList.remove('show'));
                        submenu.classList.add('show');
                    }
                });
            });

            document.addEventListener('click', function(e) {
                if (!e.target.closest('.menu-item')) {
                    document.querySelectorAll('.submenu').forEach(s => s.classList.remove('show'));
                }
            });
        }

        // Status Bar
        function updateStatusBar() {
            const now = new Date();
            document.getElementById('statusTime').textContent = now.toLocaleTimeString('ar-SA');
        }

        // Show/Hide Forms
        function hideAllForms() {
            document.querySelectorAll('[id$="Form"]').forEach(el => el.classList.add('hidden'));
            document.getElementById('welcomeForm').style.display = 'none';
        }

        function showPointOfSale() {
            hideAllForms();
            document.getElementById('posForm').classList.remove('hidden');
            setTimeout(() => document.getElementById('scannerInput').focus(), 100);
        }

        function showProductsForm() {
            hideAllForms();
            document.getElementById('productsForm').classList.remove('hidden');
            displayProductsList();
        }

        function showCustomersForm() {
            hideAllForms();
            document.getElementById('customersForm').classList.remove('hidden');
            displayCustomersList();
        }

        function showEmployeesForm() {
            hideAllForms();
            document.getElementById('employeesForm').classList.remove('hidden');
            displayEmployeesList();
        }

        function showReturns() {
            hideAllForms();
            document.getElementById('returnsForm').classList.remove('hidden');
            displayReturnsList();
        }

        function showWholesale() {
            hideAllForms();
            document.getElementById('wholesaleForm').classList.remove('hidden');
            displayWholesaleList();
        }

        function showGeneralReport() {
            hideAllForms();
            document.getElementById('reportsForm').classList.remove('hidden');
            updateReports();
        }

        function showSettings() {
            hideAllForms();
            document.getElementById('settingsForm').classList.remove('hidden');
            loadSettings();
        }

        function showUsersForm() {
            hideAllForms();
            document.getElementById('usersForm').classList.remove('hidden');
            displayUsersList();
        }

        function showPurchases() {
            showMessageBox('قريباً', 'سيتم إضافة نموذج المشتريات قريباً');
        }

        function showExpenses() {
            showMessageBox('قريباً', 'سيتم إضافة نموذج المصروفات قريباً');
        }

        function showSalesReport() {
            showGeneralReport();
        }

        function showInventoryReport() {
            showMessageBox('قريباً', 'سيتم إضافة تقرير المخزون قريباً');
        }

        function showExpensesReport() {
            showMessageBox('قريباً', 'سيتم إضافة تقرير المصروفات قريباً');
        }

        function showSuppliersForm() {
            showMessageBox('قريباً', 'سيتم إضافة نموذج الموردين قريباً');
        }

        function showAbout() {
            showMessageBox('عن البرنامج', 'منظومة مبيعات مكتبة الشروق\nالإصدار 2026 Pro\nنسخة احترافية متقدمة مع اختصارات لوحة المفاتيح\nجميع الحقوق محفوظة © 2026');
        }

        // Scanner Input
        function setupScannerInput() {
            const input = document.getElementById('scannerInput');
            input.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    const code = this.value.trim();
                    const product = appData.products.find(p => p.code === code);
                    
                    if (product) {
                        addItemToInvoice(product);
                        this.value = '';
                    } else {
                        showMessageBox('خطأ', 'المنتج غير موجود: ' + code);
                        this.value = '';
                    }
                }
            });
        }

        // Point of Sale Functions
        function addItemToInvoice(product) {
            const existingItem = currentInvoice.items.find(item => item.id === product.id);
            
            if (existingItem) {
                existingItem.quantity++;
            } else {
                currentInvoice.items.push({
                    id: product.id,
                    code: product.code,
                    name: product.name,
                    price: parseFloat(product.price),
                    quantity: 1
                });
            }
            
            updateInvoiceDisplay();
        }

        function updateInvoiceDisplay() {
            const tbody = document.getElementById('invoiceBody');
            
            if (currentInvoice.items.length === 0) {
                tbody.innerHTML = '<tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد منتجات</td></tr>';
            } else {
                tbody.innerHTML = currentInvoice.items.map((item, index) => `
                    <tr>
                        <td>${item.name}</td>
                        <td>${item.code}</td>
                        <td style="text-align: center;">
                            <input type="number" value="${item.quantity}" min="1" style="width: 50px; padding: 4px; border-radius: 3px;" onchange="updateItemQuantity(${index}, this.value)">
                        </td>
                        <td style="text-align: center;">${item.price.toFixed(2)}</td>
                        <td style="text-align: center; font-weight: 600;">${(item.quantity * item.price).toFixed(2)}</td>
                        <td style="text-align: center;">
                            <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="removeFromInvoice(${index})">حذف</button>
                        </td>
                        <td style="text-align: center;">
                            <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="editItem(${index})">تعديل</button>
                        </td>
                    </tr>
                `).join('');
            }
            
            updateInvoiceSummary();
        }

        function updateItemQuantity(index, value) {
            const qty = parseInt(value);
            if (qty > 0) {
                currentInvoice.items[index].quantity = qty;
                updateInvoiceDisplay();
            }
        }

        function removeFromInvoice(index) {
            currentInvoice.items.splice(index, 1);
            updateInvoiceDisplay();
        }

        function editItem(index) {
            editingItemIndex = index;
            const item = currentInvoice.items[index];
            document.getElementById('editPrice').value = item.price;
            document.getElementById('editQuantity').value = item.quantity;
            document.getElementById('editItemModal').classList.add('show');
        }

        function saveItemEdit() {
            if (editingItemIndex !== null) {
                const newPrice = parseFloat(document.getElementById('editPrice').value);
                const newQuantity = parseInt(document.getElementById('editQuantity').value);
                
                if (newPrice > 0 && newQuantity > 0) {
                    currentInvoice.items[editingItemIndex].price = newPrice;
                    currentInvoice.items[editingItemIndex].quantity = newQuantity;
                    updateInvoiceDisplay();
                    closeEditItemModal();
                } else {
                    showMessageBox('خطأ', 'الرجاء إدخال قيم صحيحة');
                }
            }
        }

        function closeEditItemModal() {
            document.getElementById('editItemModal').classList.remove('show');
            editingItemIndex = null;
        }

        function updateInvoiceSummary() {
            const itemCount = currentInvoice.items.length;
            const subtotal = currentInvoice.items.reduce((sum, item) => sum + (item.quantity * item.price), 0);
            const taxRate = parseFloat(document.getElementById('taxRate')?.value || 15) / 100;
            const tax = subtotal * taxRate;
            const total = subtotal + tax;

            currentInvoice.subtotal = subtotal;
            currentInvoice.tax = tax;
            currentInvoice.total = total;

            document.getElementById('itemCount').textContent = itemCount;
            document.getElementById('subtotal').textContent = subtotal.toFixed(2);
            document.getElementById('taxAmount').textContent = tax.toFixed(2);
            document.getElementById('totalAmount').textContent = total.toFixed(2);
        }

        function completeInvoice() {
            if (currentInvoice.items.length === 0) {
                showMessageBox('خطأ', 'الفاتورة فارغة');
                return;
            }

            const customer = document.getElementById('customerName').value || 'عميل نقدي';
            const paymentMethod = document.getElementById('paymentMethod').value;
            const notes = document.getElementById('invoiceNotes').value;

            currentInvoice.number = 'INV-' + (appData.sales.length + 1);
            currentInvoice.customer = customer;
            currentInvoice.paymentMethod = paymentMethod;
            currentInvoice.notes = notes;
            currentInvoice.status = 'completed';
            currentInvoice.date = new Date().toLocaleDateString('ar-SA');
            currentInvoice.time = new Date().toLocaleTimeString('ar-SA');

            appData.sales.push({...currentInvoice});
            appData.invoices.push({...currentInvoice});
            saveToStorage();
            
            showMessageBox('نجاح', 'تم إتمام الفاتورة برقم: ' + currentInvoice.number);
            clearInvoice();
        }

        function clearInvoice() {
            currentInvoice = {
                id: null,
                number: '',
                items: [],
                customer: '',
                paymentMethod: 'cash',
                notes: '',
                date: new Date().toLocaleDateString('ar-SA'),
                time: new Date().toLocaleTimeString('ar-SA'),
                subtotal: 0,
                tax: 0,
                total: 0,
                status: 'draft'
            };
            document.getElementById('customerName').value = '';
            document.getElementById('paymentMethod').value = 'cash';
            document.getElementById('invoiceNotes').value = '';
            updateInvoiceDisplay();
            document.getElementById('scannerInput').focus();
        }

        function newInvoice() {
            clearInvoice();
            showPointOfSale();
        }

        function togglePendingInvoices() {
            const modal = document.getElementById('pendingInvoicesModal');
            if (modal.classList.contains('show')) {
                modal.classList.remove('show');
            } else {
                updatePendingInvoicesList();
                modal.classList.add('show');
            }
        }

        function closePendingInvoicesModal() {
            document.getElementById('pendingInvoicesModal').classList.remove('show');
        }

        function updatePendingInvoicesList() {
            const pending = appData.invoices.filter(inv => inv.status === 'draft');
            const listDiv = document.getElementById('pendingInvoicesList');

            if (pending.length === 0) {
                listDiv.innerHTML = '<div style="padding: 8px; text-align: center; color: #868e96;">لا توجد فواتير معلقة</div>';
                return;
            }

            listDiv.innerHTML = pending.map((inv, idx) => `
                <div style="background: linear-gradient(135deg, #fff3e0 0%, #fff 100%); border: 1px solid #ffc107; border-radius: 6px; padding: 12px; margin: 8px 0;">
                    <div style="font-weight: 600; color: #fd7e14;">${inv.number || 'فاتورة ' + idx}</div>
                    <div style="font-size: 11px; color: #495057;">العميل: ${inv.customer}</div>
                    <div style="font-size: 11px; color: #495057;">المبلغ: ${inv.total.toFixed(2)}</div>
                    <div style="font-size: 11px; color: #495057;">التاريخ: ${inv.date}</div>
                    <button class="modern-button" style="width: 100%; margin-top: 8px;" onclick="loadPendingInvoice(${appData.invoices.indexOf(inv)})">فتح</button>
                </div>
            `).join('');
        }

        function loadPendingInvoice(index) {
            const invoice = appData.invoices[index];
            currentInvoice = {...invoice};
            document.getElementById('customerName').value = currentInvoice.customer;
            document.getElementById('paymentMethod').value = currentInvoice.paymentMethod;
            document.getElementById('invoiceNotes').value = currentInvoice.notes;
            updateInvoiceDisplay();
            closePendingInvoicesModal();
            showPointOfSale();
        }

        function printInvoice() {
            if (currentInvoice.items.length === 0) {
                showMessageBox('خطأ', 'الفاتورة فارغة');
                return;
            }

            const content = `
                <div style="text-align: center; padding: 20px; font-family: Arial; direction: rtl;">
                    <h2 style="margin: 0; color: #0d6efd;">📚 مكتبة الشروق</h2>
                    <p style="margin: 5px 0; font-size: 12px;">فاتورة بيع</p>
                    <hr>
                    <div style="text-align: right; margin: 15px 0;">
                        <p><strong>التاريخ:</strong> ${currentInvoice.date}</p>
                        <p><strong>الوقت:</strong> ${currentInvoice.time}</p>
                        <p><strong>العميل:</strong> ${currentInvoice.customer}</p>
                        <p><strong>رقم الفاتورة:</strong> ${currentInvoice.number}</p>
                    </div>
                    <table style="width: 100%; border-collapse: collapse; margin: 15px 0;">
                        <thead>
                            <tr style="border-bottom: 2px solid #0d6efd;">
                                <th style="padding: 8px; text-align: right;">الصنف</th>
                                <th style="padding: 8px; text-align: center;">الكمية</th>
                                <th style="padding: 8px; text-align: center;">السعر</th>
                                <th style="padding: 8px; text-align: center;">المجموع</th>
                            </tr>
                        </thead>
                        <tbody>
                            ${currentInvoice.items.map(item => `
                                <tr style="border-bottom: 1px solid #dee2e6;">
                                    <td style="padding: 6px; text-align: right;">${item.name}</td>
                                    <td style="padding: 6px; text-align: center;">${item.quantity}</td>
                                    <td style="padding: 6px; text-align: center;">${item.price.toFixed(2)}</td>
                                    <td style="padding: 6px; text-align: center;">${(item.quantity * item.price).toFixed(2)}</td>
                                </tr>
                            `).join('')}
                        </tbody>
                    </table>
                    <div style="text-align: left; border-top: 2px solid #0d6efd; padding-top: 10px; margin-top: 10px;">
                        <p><strong>الإجمالي قبل الضريبة:</strong> ${currentInvoice.subtotal.toFixed(2)}</p>
                        <p><strong>الضريبة:</strong> ${currentInvoice.tax.toFixed(2)}</p>
                        <p style="font-size: 16px; color: #0d6efd;"><strong>الإجمالي النهائي:</strong> ${currentInvoice.total.toFixed(2)}</p>
                    </div>
                    <div style="margin-top: 20px; text-align: center; font-size: 12px; color: #868e96;">
                        <p>شكراً لتعاملكم معنا</p>
                    </div>
                </div>
            `;

            const element = document.createElement('div');
            element.innerHTML = content;
            const opt = {
                margin: 10,
                filename: currentInvoice.number + '.pdf',
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2 },
                jsPDF: { orientation: 'portrait', unit: 'mm', format: 'a4' }
            };
            html2pdf().set(opt).from(element).save();
        }

        // Products Management
        function addProduct() {
            const code = document.getElementById('productCode').value;
            const name = document.getElementById('productName').value;
            const category = document.getElementById('productCategory').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const quantity = parseInt(document.getElementById('productQuantity').value);
            const supplier = document.getElementById('productSupplier').value;

            if (!code || !name || !price || isNaN(price)) {
                showMessageBox('خطأ', 'الرجاء ملء جميع الحقول المطلوبة');
                return;
            }

            const product = {
                id: Date.now(),
                code,
                name,
                category,
                price,
                quantity: quantity || 0,
                supplier,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.products.push(product);
            saveToStorage();
            displayProductsList();
            clearProductForm();
            showMessageBox('نجاح', 'تم إضافة الصنف بنجاح');
        }

        function updateProduct() {
            if (!editingProductId) {
                showMessageBox('خطأ', 'الرجاء اختيار صنف أولاً');
                return;
            }

            const product = appData.products.find(p => p.id === editingProductId);
            if (product) {
                product.code = document.getElementById('productCode').value;
                product.name = document.getElementById('productName').value;
                product.category = document.getElementById('productCategory').value;
                product.price = parseFloat(document.getElementById('productPrice').value);
                product.quantity = parseInt(document.getElementById('productQuantity').value) || 0;
                product.supplier = document.getElementById('productSupplier').value;

                saveToStorage();
                displayProductsList();
                clearProductForm();
                showMessageBox('نجاح', 'تم تحديث الصنف بنجاح');
            }
        }

        function clearProductForm() {
            document.getElementById('productCode').value = '';
            document.getElementById('productName').value = '';
            document.getElementById('productCategory').value = 'اختر الفئة';
            document.getElementById('productPrice').value = '';
            document.getElementById('productQuantity').value = '';
            document.getElementById('productSupplier').value = '';
            editingProductId = null;
        }

        function displayProductsList() {
            const tbody = document.getElementById('productsBody');
            
            if (appData.products.length === 0) {
                tbody.innerHTML = '<tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد منتجات</td></tr>';
                return;
            }

            tbody.innerHTML = appData.products.map(p => `
                <tr>
                    <td>${p.code}</td>
                    <td>${p.name}</td>
                    <td>${p.category}</td>
                    <td style="text-align: center;">${p.price.toFixed(2)}</td>
                    <td style="text-align: center;">${p.quantity}</td>
                    <td>${p.supplier || '-'}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteProduct(${p.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteProduct(id) {
            if (confirm('هل تأكد من حذف هذا الصنف؟')) {
                appData.products = appData.products.filter(p => p.id !== id);
                saveToStorage();
                displayProductsList();
            }
        }

        // Customers Management
        function addCustomer() {
            const code = document.getElementById('customerCode').value;
            const name = document.getElementById('customerNameInput').value;
            const type = document.getElementById('customerType').value;
            const phone = document.getElementById('customerPhone').value;
            const email = document.getElementById('customerEmail').value;
            const address = document.getElementById('customerAddress').value;

            if (!code || !name) {
                showMessageBox('خطأ', 'الرجاء ملء البيانات المطلوبة');
                return;
            }

            const customer = {
                id: Date.now(),
                code,
                name,
                type,
                phone,
                email,
                address,
                balance: 0,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.customers.push(customer);
            saveToStorage();
            displayCustomersList();
            clearCustomerForm();
            showMessageBox('نجاح', 'تم إضافة العميل بنجاح');
        }

        function clearCustomerForm() {
            document.getElementById('customerCode').value = '';
            document.getElementById('customerNameInput').value = '';
            document.getElementById('customerType').value = 'retail';
            document.getElementById('customerPhone').value = '';
            document.getElementById('customerEmail').value = '';
            document.getElementById('customerAddress').value = '';
        }

        function displayCustomersList() {
            const tbody = document.getElementById('customersBody');
            
            if (appData.customers.length === 0) {
                tbody.innerHTML = '<tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد عملاء</td></tr>';
                return;
            }

            const typeNames = { retail: 'تجزئة', wholesale: 'جملة', corporate: 'شركة' };

            tbody.innerHTML = appData.customers.map(c => `
                <tr>
                    <td>${c.code}</td>
                    <td>${c.name}</td>
                    <td>${typeNames[c.type]}</td>
                    <td>${c.phone || '-'}</td>
                    <td style="text-align: center; font-weight: 600;">${c.balance.toFixed(2)}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteCustomer(${c.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteCustomer(id) {
            if (confirm('هل تأكد من حذف هذا العميل؟')) {
                appData.customers = appData.customers.filter(c => c.id !== id);
                saveToStorage();
                displayCustomersList();
            }
        }

        // Employees Management
        function addEmployee() {
            const code = document.getElementById('employeeCode').value;
            const name = document.getElementById('employeeName').value;
            const position = document.getElementById('employeePosition').value;
            const salary = parseFloat(document.getElementById('employeeSalary').value);
            const phone = document.getElementById('employeePhone').value;
            const startDate = document.getElementById('employeeStartDate').value;

            if (!code || !name || !salary || isNaN(salary)) {
                showMessageBox('خطأ', 'الرجاء ملء البيانات المطلوبة');
                return;
            }

            const employee = {
                id: Date.now(),
                code,
                name,
                position,
                salary,
                phone,
                startDate,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.employees.push(employee);
            saveToStorage();
            displayEmployeesList();
            clearEmployeeForm();
            showMessageBox('نجاح', 'تم إضافة الموظف بنجاح');
        }

        function clearEmployeeForm() {
            document.getElementById('employeeCode').value = '';
            document.getElementById('employeeName').value = '';
            document.getElementById('employeePosition').value = '';
            document.getElementById('employeeSalary').value = '';
            document.getElementById('employeePhone').value = '';
            document.getElementById('employeeStartDate').value = '';
        }

        function displayEmployeesList() {
            const tbody = document.getElementById('employeesBody');
            
            if (appData.employees.length === 0) {
                tbody.innerHTML = '<tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد موظفين</td></tr>';
                return;
            }

            tbody.innerHTML = appData.employees.map(e => `
                <tr>
                    <td>${e.code}</td>
                    <td>${e.name}</td>
                    <td>${e.position}</td>
                    <td style="text-align: center;">${e.salary.toFixed(2)}</td>
                    <td>${e.startDate || '-'}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteEmployee(${e.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteEmployee(id) {
            if (confirm('هل تأكد من حذف هذا الموظف؟')) {
                appData.employees = appData.employees.filter(e => e.id !== id);
                saveToStorage();
                displayEmployeesList();
            }
        }

        // Returns Management
        function addReturn() {
            const code = document.getElementById('returnCode').value;
            const product = document.getElementById('returnProduct').value;
            const quantity = parseInt(document.getElementById('returnQuantity').value);
            const reason = document.getElementById('returnReason').value;

            if (!code || !product || !quantity || isNaN(quantity)) {
                showMessageBox('خطأ', 'الرجاء ملء البيانات المطلوبة');
                return;
            }

            const returnRecord = {
                id: Date.now(),
                code,
                product,
                quantity,
                reason,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.returns.push(returnRecord);
            saveToStorage();
            displayReturnsList();
            clearReturnForm();
            showMessageBox('نجاح', 'تم تسجيل الترجيع بنجاح');
        }

        function clearReturnForm() {
            document.getElementById('returnCode').value = '';
            document.getElementById('returnProduct').value = '';
            document.getElementById('returnQuantity').value = '';
            document.getElementById('returnReason').value = '';
        }

        function displayReturnsList() {
            const tbody = document.getElementById('returnsBody');
            
            if (appData.returns.length === 0) {
                tbody.innerHTML = '<tr><td colspan="6" style="text-align: center; padding: 8px;">لا توجد ترجيعات</td></tr>';
                return;
            }

            tbody.innerHTML = appData.returns.map(r => `
                <tr>
                    <td>${r.code}</td>
                    <td>${r.product}</td>
                    <td style="text-align: center;">${r.quantity}</td>
                    <td>${r.reason}</td>
                    <td>${r.date}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteReturn(${r.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteReturn(id) {
            if (confirm('هل تأكد من حذف هذا الترجيع؟')) {
                appData.returns = appData.returns.filter(r => r.id !== id);
                saveToStorage();
                displayReturnsList();
            }
        }

        // Wholesale Management
        function addWholesale() {
            const customer = document.getElementById('wholesaleCustomer').value;
            const product = document.getElementById('wholesaleProduct').value;
            const quantity = parseInt(document.getElementById('wholesaleQuantity').value);
            const discount = parseFloat(document.getElementById('wholesaleDiscount').value) || 0;

            if (!customer || !product || !quantity || isNaN(quantity)) {
                showMessageBox('خطأ', 'الرجاء ملء البيانات المطلوبة');
                return;
            }

            const prod = appData.products.find(p => p.name === product);
            if (!prod) {
                showMessageBox('خطأ', 'الصنف غير موجود');
                return;
            }

            const subtotal = quantity * prod.price;
            const discountAmount = (subtotal * discount) / 100;
            const total = subtotal - discountAmount;

            const wholesale = {
                id: Date.now(),
                customer,
                product,
                quantity,
                discount,
                subtotal,
                discountAmount,
                total,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.wholesale.push(wholesale);
            saveToStorage();
            displayWholesaleList();
            clearWholesaleForm();
            showMessageBox('نجاح', 'تم إنشاء طلب الجملة بنجاح');
        }

        function clearWholesaleForm() {
            document.getElementById('wholesaleCustomer').value = '';
            document.getElementById('wholesaleProduct').value = '';
            document.getElementById('wholesaleQuantity').value = '';
            document.getElementById('wholesaleDiscount').value = '';
        }

        function displayWholesaleList() {
            const tbody = document.getElementById('wholesaleBody');
            
            if (appData.wholesale.length === 0) {
                tbody.innerHTML = '<tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد طلبات</td></tr>';
                return;
            }

            tbody.innerHTML = appData.wholesale.map(w => `
                <tr>
                    <td>${w.customer}</td>
                    <td>${w.product}</td>
                    <td style="text-align: center;">${w.quantity}</td>
                    <td style="text-align: center;">${w.discount}%</td>
                    <td style="text-align: center; font-weight: 600;">${w.total.toFixed(2)}</td>
                    <td>${w.date}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteWholesale(${w.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteWholesale(id) {
            if (confirm('هل تأكد من حذف هذا الطلب؟')) {
                appData.wholesale = appData.wholesale.filter(w => w.id !== id);
                saveToStorage();
                displayWholesaleList();
            }
        }

        // Reports
        function updateReports() {
            const totalSales = appData.sales.reduce((sum, s) => sum + s.total, 0);
            const totalExpenses = appData.expenses.reduce((sum, e) => sum + e.amount, 0);
            const netProfit = totalSales - totalExpenses;

            document.getElementById('totalSales').textContent = totalSales.toFixed(2);
            document.getElementById('totalExpenses').textContent = totalExpenses.toFixed(2);
            document.getElementById('netProfit').textContent = netProfit.toFixed(2);

            displaySalesReport();
        }

        function displaySalesReport() {
            const tbody = document.getElementById('salesReportBody');
            
            if (appData.sales.length === 0) {
                tbody.innerHTML = '<tr><td colspan="7" style="text-align: center; padding: 8px;">لا توجد مبيعات</td></tr>';
                return;
            }

            const paymentNames = { cash: 'نقداً', card: 'بطاقة', check: 'شيك', credit: 'على الحساب' };

            tbody.innerHTML = appData.sales.map(s => `
                <tr>
                    <td>${s.number || 'INV-' + s.id}</td>
                    <td>${s.customer}</td>
                    <td style="text-align: center;">${s.subtotal.toFixed(2)}</td>
                    <td style="text-align: center;">${s.tax.toFixed(2)}</td>
                    <td style="text-align: center; font-weight: 600;">${s.total.toFixed(2)}</td>
                    <td>${paymentNames[s.paymentMethod]}</td>
                    <td>${s.date}</td>
                </tr>
            `).join('');
        }

        function printReport() {
            window.print();
        }

        function exportReport() {
            const csv = generateCSV(appData.sales);
            downloadCSV(csv, 'sales_report.csv');
        }

        function generateCSV(data) {
            const headers = ['رقم الفاتورة', 'العميل', 'المبلغ', 'الضريبة', 'الإجمالي', 'طريقة الدفع', 'التاريخ'];
            const rows = data.map(s => [
                s.number || s.id,
                s.customer,
                s.subtotal.toFixed(2),
                s.tax.toFixed(2),
                s.total.toFixed(2),
                s.paymentMethod,
                s.date
            ]);

            let csv = headers.join(',') + '\n';
            rows.forEach(row => csv += row.join(',') + '\n');
            return csv;
        }

        function downloadCSV(csv, filename) {
            const blob = new Blob([csv], { type: 'text/csv' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.download = filename;
            link.click();
        }

        // Users Management
        function addUser() {
            const name = document.getElementById('userName').value;
            const password = document.getElementById('userPassword').value;
            const role = document.getElementById('userRole').value;
            const email = document.getElementById('userEmail').value;

            if (!name || !password) {
                showMessageBox('خطأ', 'الرجاء ملء جميع الحقول');
                return;
            }

            const user = {
                id: Date.now(),
                name,
                password,
                role,
                email,
                date: new Date().toLocaleDateString('ar-SA')
            };

            appData.users.push(user);
            saveToStorage();
            displayUsersList();
            clearUserForm();
            showMessageBox('نجاح', 'تم إضافة المستخدم بنجاح');
        }

        function clearUserForm() {
            document.getElementById('userName').value = '';
            document.getElementById('userPassword').value = '';
            document.getElementById('userRole').value = 'cashier';
            document.getElementById('userEmail').value = '';
        }

        function displayUsersList() {
            const tbody = document.getElementById('usersBody');
            
            if (appData.users.length === 0) {
                tbody.innerHTML = '<tr><td colspan="4" style="text-align: center; padding: 8px;">لا توجد مستخدمين</td></tr>';
                return;
            }

            const roleNames = { admin: 'مدير', cashier: 'أمين صندوق', manager: 'مدير مستخدمين', viewer: 'عارض فقط' };

            tbody.innerHTML = appData.users.map(u => `
                <tr>
                    <td>${u.name}</td>
                    <td>${u.email || '-'}</td>
                    <td>${roleNames[u.role]}</td>
                    <td style="text-align: center;">
                        <button class="modern-button" style="padding: 4px 8px; font-size: 11px; min-width: auto;" onclick="deleteUser(${u.id})">حذف</button>
                    </td>
                </tr>
            `).join('');
        }

        function deleteUser(id) {
            if (confirm('هل تأكد من حذف هذا المستخدم؟')) {
                appData.users = appData.users.filter(u => u.id !== id);
                saveToStorage();
                displayUsersList();
            }
        }

        // Settings
        function loadSettings() {
            const settings = JSON.parse(localStorage.getItem('appSettings') || '{}');
            document.getElementById('companyName').value = settings.companyName || 'مكتبة الشروق';
            document.getElementById('companyPhone').value = settings.companyPhone || '';
            document.getElementById('companyEmail').value = settings.companyEmail || '';
            document.getElementById('companyAddress').value = settings.companyAddress || '';
            document.getElementById('taxRate').value = settings.taxRate || 15;
            document.getElementById('currency').value = settings.currency || 'ريال';
        }

        function saveSettings() {
            const settings = {
                companyName: document.getElementById('companyName').value,
                companyPhone: document.getElementById('companyPhone').value,
                companyEmail: document.getElementById('companyEmail').value,
                companyAddress: document.getElementById('companyAddress').value,
                taxRate: document.getElementById('taxRate').value,
                currency: document.getElementById('currency').value
            };
            localStorage.setItem('appSettings', JSON.stringify(settings));
            showMessageBox('نجاح', 'تم حفظ الإعدادات بنجاح');
        }

        // Storage Management
        function saveToStorage() {
            localStorage.setItem('bookstorePOS', JSON.stringify(appData));
        }

        function loadFromStorage() {
            const stored = localStorage.getItem('bookstorePOS');
            if (stored) {
                appData = JSON.parse(stored);
            }
        }

        function exportBackup() {
            const backup = JSON.stringify(appData, null, 2);
            const blob = new Blob([backup], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.download = 'bookstore_backup_' + new Date().getTime() + '.json';
            link.click();
        }

        function importBackup() {
            document.getElementById('importFileInput').click();
        }

        function importBackupFile(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const imported = JSON.parse(e.target.result);
                    if (imported.products) {
                        appData = imported;
                        saveToStorage();
                        showMessageBox('نجاح', 'تم استيراد البيانات بنجاح');
                        displayAllLists();
                    }
                } catch (error) {
                    showMessageBox('خطأ', 'خطأ في الاستيراد: ' + error.message);
                }
            };
            reader.readAsText(file);
        }

        function clearAllData() {
            if (confirm('هل تأكد من مسح جميع البيانات؟ لا يمكن التراجع عن هذا الإجراء')) {
                appData = {
                    products: [],
                    customers: [],
                    employees: [],
                    sales: [],
                    returns: [],
                    wholesale: [],
                    expenses: [],
                    assets: [],
                    bankTransactions: [],
                    imports: [],
                    users: [],
                    invoices: [],
                    purchases: []
                };
                saveToStorage();
                displayAllLists();
                showMessageBox('تم', 'تم مسح جميع البيانات');
            }
        }

        function displayAllLists() {
            displayProductsList();
            displayCustomersList();
            displayEmployeesList();
            displayReturnsList();
            displayWholesaleList();
            displayUsersList();
            updateReports();
        }

        // File Operations
        function saveFile() {
            showMessageBox('تم', 'تم حفظ البيانات بنجاح');
        }

        function openFile() {
            showMessageBox('معلومة', 'هذه الميزة قيد التطوير');
        }

        function undo() {
            showMessageBox('معلومة', 'هذه الميزة قيد التطوير');
        }

        function redo() {
            showMessageBox('معلومة', 'هذه الميزة قيد التطوير');
        }

        function exitApp() {
            if (confirm('هل تريد الخروج من البرنامج؟')) {
                window.close();
            }
        }

        // Message Box
        function showMessageBox(title, message) {
            document.getElementById('messageTitle').textContent = title;
            document.getElementById('messageContent').textContent = message;
            document.getElementById('messageBox').classList.add('show');
        }

        function closeMessageBox() {
            document.getElementById('messageBox').classList.remove('show');
        }
    </script>
</body>
</html>
