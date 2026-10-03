<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نيو فيوتشر بلاست · للصناعات البلاستيكية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Reem+Kufi:wght@400;500;600;700&family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-light: #F9FAFB;
            --bg-warm: #F3F4F6;
            --bg-card: rgba(255, 255, 255, 0.75);
            --border-glass: rgba(0, 0, 0, 0.06);
            --gold-deep: #B8860B;
            --gold-bright: #D4AF37;
            --gold-light: #F5C242;
            --text-main: #1F2937;
            --text-soft: #4B5563;
            --text-faded: #9CA3AF;
            --blue-accent: #3B82F6;
            --red-accent: #EF4444;
            --green-accent: #10B981;
            --whatsapp: #25D366;
        }

        * {
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--bg-light);
            background-image: 
                radial-gradient(circle at 10% 10%, rgba(212, 175, 55, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 90% 90%, rgba(59, 130, 246, 0.05) 0%, transparent 45%);
            color: var(--text-main);
            min-height: 100vh;
            line-height: 1.8;
            overflow-x: hidden;
        }

        .display-font { font-family: 'Reem Kufi', sans-serif; font-weight: 700; }
        
        /* Animated Background Orbs (Light Mode) */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            z-index: -1;
            opacity: 0.5;
            animation: float 14s ease-in-out infinite;
        }
        .orb-1 { width: 400px; height: 400px; background: radial-gradient(circle, #F5C242, transparent); top: -100px; right: -100px; }
        .orb-2 { width: 300px; height: 300px; background: radial-gradient(circle, #60A5FA, transparent); bottom: -50px; left: -50px; animation-delay: 6s; }
        
        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            50% { transform: translate(30px, 20px) scale(1.05); }
        }

        /* Glass Card System (Light) */
        .glass-card {
            background: var(--bg-card);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--border-glass);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.04), 0 1px 3px rgba(0, 0, 0, 0.02);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .glass-card:hover {
            border-color: rgba(212, 175, 55, 0.3);
            background: rgba(255, 255, 255, 0.9);
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.08), 0 0 0 1px rgba(212, 175, 55, 0.1);
        }

        /* Gold Gradient Text */
        .text-gold {
            background: linear-gradient(135deg, #B8860B 0%, #D4AF37 50%, #B8860B 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .btn-glow {
            box-shadow: 0 0 0 rgba(212, 175, 55, 0.0);
            transition: all 0.3s ease;
        }
        .btn-glow:hover {
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.2);
            transform: translateY(-2px);
        }

        /* Bank Accents */
        .bank-blue { border-right: 3px solid var(--blue-accent); }
        .bank-blue:hover { border-right-color: #60A5FA; }
        .bank-red { border-right: 3px solid var(--red-accent); }
        .bank-red:hover { border-right-color: #F87171; }
        .bank-green { border-right: 3px solid var(--green-accent); }
        .bank-green:hover { border-right-color: #34D399; }

        /* Expandable Bank */
        .bank-details {
            max-height: 0;
            overflow: hidden;
            opacity: 0;
            transition: max-height 0.6s ease, opacity 0.4s ease 0.1s;
        }
        .bank-card.expanded .bank-details {
            max-height: 800px;
            opacity: 1;
        }
        .bank-card.expanded .expand-icon { transform: rotate(180deg); }
        .expand-icon { transition: transform 0.4s ease; }

        /* Fade Up Animation */
        .fade-up {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }
        .fade-up.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Copy Buttons (Light) */
        .copy-btn {
            transition: all 0.3s ease;
        }
        .copy-blue { background: rgba(59, 130, 246, 0.1); color: #2563EB; border: 1px solid rgba(59, 130, 246, 0.2); }
        .copy-blue:hover { background: var(--blue-accent); color: white; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.2); }
        .copy-red { background: rgba(239, 68, 68, 0.1); color: #DC2626; border: 1px solid rgba(239, 68, 68, 0.2); }
        .copy-red:hover { background: var(--red-accent); color: white; box-shadow: 0 4px 12px rgba(239, 68, 68, 0.2); }
        .copy-green { background: rgba(16, 185, 129, 0.1); color: #059669; border: 1px solid rgba(16, 185, 129, 0.2); }
        .copy-green:hover { background: var(--green-accent); color: white; box-shadow: 0 4px 12px rgba(16, 185, 129, 0.2); }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%) translateY(150px);
            background: rgba(30, 30, 30, 0.95);
            backdrop-filter: blur(10px);
            color: white;
            padding: 1rem 2rem;
            border-radius: 12px;
            font-size: 0.9rem;
            box-shadow: 0 10px 40px rgba(0,0,0,0.2);
            transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            z-index: 100;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .toast.show { transform: translateX(-50%) translateY(0); }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #F9FAFB; }
        ::-webkit-scrollbar-thumb { background: #D1D5DB; border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--gold-deep); }

        /* Logo Box 3D (Light) */
        .logo-box {
            background: linear-gradient(145deg, #FFFFFF, #F3F4F6);
            border: 1px solid var(--border-glass);
            box-shadow: 
                8px 8px 16px rgba(0,0,0,0.06), 
                -8px -8px 16px rgba(255,255,255,0.9),
                inset 0 1px 1px rgba(255,255,255,0.5);
            position: relative;
            overflow: hidden;
        }
        .logo-box::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(212, 175, 55, 0.15), transparent);
            transform: rotate(45deg);
            transition: all 0.5s ease;
            opacity: 0;
        }
        .logo-box:hover::after {
            opacity: 1;
            transform: rotate(45deg) translate(50%, 50%);
        }

        /* Developer Section Styles */
        .dev-link {
            transition: all 0.3s ease;
        }
        .dev-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
        }
        .whatsapp-btn { background: var(--whatsapp); }
        .whatsapp-btn:hover { background: #128C7E; box-shadow: 0 8px 20px rgba(37, 211, 102, 0.3); }
        .phone-btn { background: var(--blue-accent); }
        .phone-btn:hover { background: #2563EB; box-shadow: 0 8px 20px rgba(59, 130, 246, 0.3); }
        .facebook-btn { background: #1877F2; }
        .facebook-btn:hover { background: #0E5FC2; box-shadow: 0 8px 20px rgba(24, 119, 242, 0.3); }
        
        .profile-img-ring {
            background: linear-gradient(135deg, var(--gold-bright), var(--gold-deep));
            padding: 3px;
            border-radius: 50%;
        }
    </style>
</head>
<body class="px-4 py-8 sm:py-12">

    <!-- Background Orbs -->
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>

    <!-- Toast -->
    <div id="toast" class="toast">
        <i class="fa-solid fa-check text-green-400"></i>
        <span id="toastText">تم النسخ بنجاح</span>
    </div>

    <div class="max-w-5xl mx-auto space-y-8">

        <!-- ═══════════ HEADER & LOGO ═══════════ -->
        <header class="glass-card rounded-3xl p-8 sm:p-12 text-center fade-up">
            <div class="flex flex-col items-center">
                <!-- Logo Box -->
                <div class="logo-box w-36 h-36 sm:w-40 sm:h-40 rounded-3xl p-6 mb-8 flex flex-col items-center justify-center text-center">
                    <div class="w-12 h-12 rounded-xl flex items-center justify-center mb-2 shadow-lg bg-gradient-to-br from-amber-400 to-yellow-600">
                        <i class="fa-solid fa-industry text-white text-xl"></i>
                    </div>
                    <span class="text-[10px] tracking-[0.3em] text-amber-600 font-bold uppercase">NEW FUTURE</span>
                    <span class="text-sm font-black text-gray-800 tracking-wider display-font">Plast</span>
                </div>
                
                <h1 class="display-font text-4xl sm:text-6xl mb-3 text-gray-900">
                    نيو فيوتشر بلاست
                </h1>
                <p class="text-lg text-gold font-medium mb-8">للصناعات البلاستيكية</p>

                <!-- Info Badges -->
                <div class="flex flex-wrap justify-center gap-3 mb-8">
                    <span class="bg-white px-4 py-2 rounded-lg text-xs text-gray-700 border border-gray-200 flex items-center gap-2 shadow-sm">
                        <i class="fa-solid fa-file-invoice text-amber-500"></i>
                        سجل: 96178
                    </span>
                    <span class="bg-white px-4 py-2 rounded-lg text-xs text-gray-700 border border-gray-200 flex items-center gap-2 shadow-sm">
                        <i class="fa-solid fa-receipt text-amber-500"></i>
                        بطاقة ضريبية: 860-099-528
                    </span>
                </div>

                <!-- Quick Action Buttons -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-3 w-full max-w-2xl">
                    <a href="https://newfutureplast.net/" target="_blank" class="btn-glow flex items-center justify-center gap-2 bg-white hover:bg-gray-50 text-gray-800 py-3.5 px-4 rounded-xl border border-gray-200 text-sm font-medium">
                        <i class="fa-solid fa-globe text-amber-500"></i> الموقع الرسمي
                    </a>
                    <a href="https://www.facebook.com/new.future.plast" target="_blank" class="btn-glow flex items-center justify-center gap-2 bg-white hover:bg-gray-50 text-gray-800 py-3.5 px-4 rounded-xl border border-gray-200 text-sm font-medium">
                        <i class="fa-brands fa-facebook text-blue-600"></i> صفحة الفيسبوك
                    </a>
                    <a href="https://maps.app.goo.gl/e7odhL8sBjGQmf5V9" target="_blank" class="btn-glow flex items-center justify-center gap-2 bg-white hover:bg-gray-50 text-gray-800 py-3.5 px-4 rounded-xl border border-gray-200 text-sm font-medium">
                        <i class="fa-solid fa-location-dot text-red-500"></i> الموقع على الخريطة
                    </a>
                </div>
            </div>
        </header>

        <!-- ═══════════ QR CODES ═══════════ -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 fade-up">
            <!-- Page QR -->
            <div class="glass-card rounded-3xl p-6 flex flex-col items-center text-center">
                <div class="inline-flex items-center gap-2 bg-amber-100 text-amber-700 px-4 py-1.5 rounded-full text-xs font-bold border border-amber-200 mb-5">
                    <i class="fa-solid fa-qrcode"></i> QR هذه الصفحة
                </div>
                <div class="bg-white p-4 rounded-2xl shadow-xl mb-4 transition-transform hover:scale-105 duration-300 border border-gray-100">
                    <img id="pageQrImg" src="" alt="Page QR Code" class="w-32 h-32 rounded-lg">
                </div>
                <p class="text-xs text-gray-500 leading-relaxed">امسح الكود لمشاركة هذا الملف بسهولة في أي مكان.</p>
            </div>

            <!-- Location QR -->
            <div class="glass-card rounded-3xl p-6 flex flex-col items-center text-center">
                <div class="inline-flex items-center gap-2 bg-red-100 text-red-600 px-4 py-1.5 rounded-full text-xs font-bold border border-red-200 mb-5">
                    <i class="fa-solid fa-location-dot"></i> QR لوكيشن المصنع
                </div>
                <div class="bg-white p-4 rounded-2xl shadow-xl mb-4 transition-transform hover:scale-105 duration-300 border border-gray-100">
                    <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://maps.app.goo.gl/e7odhL8sBjGQmf5V9" alt="Location QR Code" class="w-32 h-32 rounded-lg">
                </div>
                <p class="text-xs text-gray-500 leading-relaxed">امسح الكود للوصول إلى المصنع بمدينة السادات مباشرة.</p>
            </div>
        </div>

        <!-- ═══════════ BANK ACCOUNTS ═══════════ -->
        <section class="fade-up">
            <div class="text-center mb-8">
                <h2 class="display-font text-3xl sm:text-4xl text-gray-900 mb-2">الحسابات البنكية المعتمدة</h2>
                <p class="text-sm text-gray-500">اضغط على البطاقة لعرض كافة التفاصيل والـ Swift Code</p>
            </div>

            <div class="space-y-4">

                <!-- Bank 1: Credit Agricole -->
                <div class="glass-card bank-blue bank-card rounded-2xl p-6 cursor-pointer" data-bank="1">
                    <div class="flex items-center justify-between" onclick="toggleBank(1)">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-blue-50 flex items-center justify-center text-blue-600 border border-blue-100">
                                <i class="fa-solid fa-landmark"></i>
                            </div>
                            <div>
                                <h3 class="display-font text-xl text-gray-900">بنك كريدي أجريكول</h3>
                                <p class="text-xs text-gray-500">فرع طنطا · مصر</p>
                            </div>
                        </div>
                        <i class="fa-solid fa-chevron-down expand-icon text-blue-500 text-sm"></i>
                    </div>

                    <div class="bank-details">
                        <div class="border-t border-gray-100 mt-5 pt-5">
                            <div class="mb-4 flex items-center gap-2 text-xs text-gray-500">
                                <i class="fa-solid fa-user text-gray-400"></i>
                                اسم الحساب: <span class="font-semibold text-gray-800">نيو فيوتشر بلاست للصناعات البلاستيكية</span>
                            </div>

                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب (Account No)</p>
                                    <p class="text-lg font-bold text-gray-900 tracking-wider mb-3" dir="ltr">11018180044559</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('11018180044559', this)" class="copy-btn copy-blue w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ رقم الحساب
                                    </button>
                                </div>
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب الدولي (IBAN)</p>
                                    <p class="text-sm font-bold text-blue-600 tracking-wider mb-3 break-all" dir="ltr">EG330036000100011018180044559</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('EG330036000100011018180044559', this)" class="copy-btn copy-blue w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ الـ IBAN
                                    </button>
                                </div>
                            </div>
                            
                            <div class="mt-4 bg-blue-50 p-3 rounded-lg border border-blue-100 flex items-center justify-between">
                                <span class="text-xs text-gray-500 flex items-center gap-2"><i class="fa-solid fa-circle-info text-blue-500"></i> Swift Code</span>
                                <span class="text-sm font-bold text-gray-800 tracking-wider" dir="ltr">AGRIGEGCXXX</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Bank 2: NBE -->
                <div class="glass-card bank-red bank-card rounded-2xl p-6 cursor-pointer" data-bank="2">
                    <div class="flex items-center justify-between" onclick="toggleBank(2)">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-red-50 flex items-center justify-center text-red-600 border border-red-100">
                                <i class="fa-solid fa-landmark"></i>
                            </div>
                            <div>
                                <h3 class="display-font text-xl text-gray-900">البنك الأهلي المصري</h3>
                                <p class="text-xs text-gray-500">فرع طنطا · مصر</p>
                            </div>
                        </div>
                        <i class="fa-solid fa-chevron-down expand-icon text-red-500 text-sm"></i>
                    </div>

                    <div class="bank-details">
                        <div class="border-t border-gray-100 mt-5 pt-5">
                            <div class="mb-4 flex items-center gap-2 text-xs text-gray-500">
                                <i class="fa-solid fa-user text-gray-400"></i>
                                اسم الحساب: <span class="font-semibold text-gray-800">نيو فيوتشر بلاست للصناعات البلاستيكية</span>
                            </div>

                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب (Account No)</p>
                                    <p class="text-lg font-bold text-gray-900 tracking-wider mb-3" dir="ltr">3793070818166001018</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('3793070818166001018', this)" class="copy-btn copy-red w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ رقم الحساب
                                    </button>
                                </div>
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب الدولي (IBAN)</p>
                                    <p class="text-sm font-bold text-red-600 tracking-wider mb-3 break-all" dir="ltr">EG640003037930708181660010180</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('EG640003037930708181660010180', this)" class="copy-btn copy-red w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ الـ IBAN
                                    </button>
                                </div>
                            </div>

                            <div class="mt-4 bg-red-50 p-3 rounded-lg border border-red-100 flex items-center justify-between">
                                <span class="text-xs text-gray-500 flex items-center gap-2"><i class="fa-solid fa-circle-info text-red-500"></i> Swift Code</span>
                                <span class="text-sm font-bold text-gray-800 tracking-wider" dir="ltr">NBEGEGCXXX</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Bank 3: Banque Misr -->
                <div class="glass-card bank-green bank-card rounded-2xl p-6 cursor-pointer" data-bank="3">
                    <div class="flex items-center justify-between" onclick="toggleBank(3)">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-green-50 flex items-center justify-center text-green-600 border border-green-100">
                                <i class="fa-solid fa-landmark"></i>
                            </div>
                            <div>
                                <h3 class="display-font text-xl text-gray-900">بنك مصر</h3>
                                <p class="text-xs text-gray-500">فرع طنطا · مصر</p>
                            </div>
                        </div>
                        <i class="fa-solid fa-chevron-down expand-icon text-green-500 text-sm"></i>
                    </div>

                    <div class="bank-details">
                        <div class="border-t border-gray-100 mt-5 pt-5">
                            <div class="mb-4 flex items-center gap-2 text-xs text-gray-500">
                                <i class="fa-solid fa-user text-gray-400"></i>
                                اسم الحساب: <span class="font-semibold text-gray-800">نيو فيوتشر بلاست للصناعات البلاستيكية</span>
                            </div>

                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب (Account No)</p>
                                    <p class="text-lg font-bold text-gray-900 tracking-wider mb-3" dir="ltr">2620240000001118</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('2620240000001118', this)" class="copy-btn copy-green w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ رقم الحساب
                                    </button>
                                </div>
                                <div class="bg-gray-50 p-4 rounded-xl border border-gray-100">
                                    <p class="text-xs text-gray-500 mb-2">رقم الحساب الدولي (IBAN)</p>
                                    <p class="text-sm font-bold text-green-600 tracking-wider mb-3 break-all" dir="ltr">EG11000202620262040000001118</p>
                                    <button onclick="event.stopPropagation(); copyToClipboard('EG11000202620262040000001118', this)" class="copy-btn copy-green w-full py-2 rounded-lg text-xs font-bold flex items-center justify-center gap-2">
                                        <i class="fa-regular fa-copy"></i> نسخ الـ IBAN
                                    </button>
                                </div>
                            </div>

                            <div class="mt-4 bg-green-50 p-3 rounded-lg border border-green-100 flex items-center justify-between">
                                <span class="text-xs text-gray-500 flex items-center gap-2"><i class="fa-solid fa-circle-info text-green-500"></i> Swift Code</span>
                                <span class="text-sm font-bold text-gray-800 tracking-wider" dir="ltr">BMISEGCAXXX</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ═══════════ DEVELOPER PROFILE ═══════════ -->
        <section class="fade-up">
            <div class="w-full h-px bg-gradient-to-r from-transparent via-gray-300 to-transparent mb-8"></div>
            
            <div class="glass-card rounded-3xl p-8 text-center">
                <p class="text-xs text-gray-400 mb-6 tracking-widest uppercase">Designed & Developed by</p>
                
                <div class="flex flex-col items-center">
                    <!-- Profile Avatar -->
                    <div class="profile-img-ring mb-4">
                        <div class="w-20 h-20 rounded-full bg-gray-100 flex items-center justify-center text-3xl text-gray-700 border-4 border-white">
                            <i class="fa-solid fa-user-tie"></i>
                        </div>
                    </div>
                    
                    <h3 class="display-font text-2xl text-gray-900 mb-1">أحمد تركى</h3>
                    <p class="text-sm text-gray-500 mb-6">مطور واجهات المستخدم</p>

                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-3 w-full max-w-xl">
                        <!-- WhatsApp -->
                        <a href="https://wa.me/201063452649" target="_blank" class="dev-link whatsapp-btn text-white flex items-center justify-center gap-2 py-3.5 px-4 rounded-xl text-sm font-bold">
                            <i class="fa-brands fa-whatsapp text-lg"></i> تواصل واتساب
                        </a>
                        <!-- Phone -->
                        <a href="tel:+201063452649" class="dev-link phone-btn text-white flex items-center justify-center gap-2 py-3.5 px-4 rounded-xl text-sm font-bold">
                            <i class="fa-solid fa-phone text-sm"></i> اتصال مباشر
                        </a>
                        <!-- Facebook -->
                        <a href="https://www.facebook.com/share/1ERhdn651k/" target="_blank" class="dev-link facebook-btn text-white flex items-center justify-center gap-2 py-3.5 px-4 rounded-xl text-sm font-bold">
                            <i class="fa-brands fa-facebook text-lg"></i> فيسبوك
                        </a>
                    </div>

                    <!-- Mobile Number display with copy -->
                    <div class="mt-6 bg-gray-50 border border-gray-100 rounded-xl py-2.5 px-4 flex items-center gap-3">
                        <span class="text-xs text-gray-500">رقم الموبايل:</span>
                        <span class="text-sm font-bold text-gray-800" dir="ltr">01063452649</span>
                        <button onclick="copyToClipboard('01063452649', this)" class="text-gray-400 hover:text-blue-500 transition-colors">
                            <i class="fa-regular fa-copy text-sm"></i>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- ═══════════ FOOTER ═══════════ -->
        <footer class="text-center py-8 fade-up">
            <div class="space-y-3 text-sm text-gray-500">
                <p class="flex items-start justify-center gap-2.5">
                    <i class="fa-solid fa-location-dot text-amber-500 mt-1"></i>
                    <span>المصانع: قطعة رقم 7077 - المنطقة الصناعية السابعة - مدينة السادات - المنوفية</span>
                </p>
                <p class="flex items-center justify-center gap-2">
                    <i class="fa-solid fa-envelope text-amber-500"></i>
                    <span dir="ltr" class="font-medium">Future_plastic@hotmail.com</span>
                </p>
            </div>
            <p class="mt-8 text-xs text-gray-400">© 2026 نيو فيوتشر بلاست للصناعات البلاستيكية. جميع الحقوق محفوظة.</p>
        </footer>
    </div>

    <script>
        // ═══════ Fade Up on Scroll ═══════
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

        // ═══════ Bank Toggle ═══════
        function toggleBank(id) {
            const card = document.querySelector(`[data-bank="${id}"]`);
            card.classList.toggle('expanded');
        }

        // ═══════ Copy to Clipboard ═══════
        function copyToClipboard(text, button) {
            navigator.clipboard.writeText(text).then(() => {
                showToast('تم النسخ بنجاح');
                
                // Visual feedback on button if it's a full button
                if(button && button.classList.contains('copy-btn')) {
                    const originalHTML = button.innerHTML;
                    button.innerHTML = '<i class="fa-solid fa-check"></i> تم النسخ';
                    button.classList.add('!bg-green-500', '!text-white', '!border-transparent', '!shadow-md');
                    
                    setTimeout(() => {
                        button.innerHTML = originalHTML;
                        button.classList.remove('!bg-green-500', '!text-white', '!border-transparent', '!shadow-md');
                    }, 2000);
                } else if (button) {
                    // Small icon copy feedback
                    const originalClass = button.innerHTML;
                    button.innerHTML = '<i class="fa-solid fa-check text-green-500 text-sm"></i>';
                    setTimeout(() => {
                        button.innerHTML = originalClass;
                    }, 1500);
                }
            }).catch(err => {
                showToast('حدث خطأ، حاول مرة أخرى');
            });
        }

        // ═══════ Toast Notification ═══════
        function showToast(message) {
            const toast = document.getElementById('toast');
            const toastText = document.getElementById('toastText');
            toastText.textContent = message;
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 2400);
        }

        // ═══════ Dynamic QR Code Generation ═══════
        window.addEventListener('DOMContentLoaded', () => {
            const currentUrl = window.location.href;
            const qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&color=000000&bgcolor=FFFFFF&data=${encodeURIComponent(currentUrl)}`;
            document.getElementById('pageQrImg').src = qrUrl;
        });
    </script>
</body>
</html>
