<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة الدكتوراه المهنية DBA - 2026</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Cairo', sans-serif; }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 flex h-screen overflow-hidden">

    <!-- Sidebar -->
    <aside class="w-72 bg-slate-900 text-white flex flex-col justify-between hidden md:flex shadow-xl">
        <div>
            <div class="p-6 border-b border-slate-800 text-center">
                <h1 class="text-lg font-black text-amber-400 tracking-wide">الدكتوراة المهنية DBA</h1>
                <p class="text-xs text-slate-400 mt-1">عام 2026</p>
            </div>
            <nav class="p-4 space-y-2" id="nav-subjects">
                <button onclick="switchSubject(1)" class="subject-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-semibold transition-all bg-amber-500 text-slate-900 shadow-lg" data-target="1">
                    <i class="fa-solid fa-chart-line w-5"></i>
                    <span class="text-xs text-right">الاتجاهات الحديثة في التمويل والاستثمار</span>
                </button>
                <button onclick="switchSubject(2)" class="subject-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-semibold transition-all text-slate-300 hover:bg-slate-800 hover:text-white" data-target="2">
                    <i class="fa-solid fa-chess-board w-5"></i>
                    <span class="text-xs text-right">المادة الثانية</span>
                </button>
                <button onclick="switchSubject(3)" class="subject-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-semibold transition-all text-slate-300 hover:bg-slate-800 hover:text-white" data-target="3">
                    <i class="fa-solid fa-network-wired w-5"></i>
                    <span class="text-xs text-right">دراسات متقدمة في التنظيم</span>
                </button>
                <button onclick="switchSubject(4)" class="subject-btn w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-semibold transition-all text-slate-300 hover:bg-slate-800 hover:text-white" data-target="4">
                    <i class="fa-solid fa-scale-balanced w-5"></i>
                    <span class="text-xs text-right">قضايا اقتصادية معاصرة</span>
                </button>
            </nav>
        </div>
        <div class="p-4 border-t border-slate-800 text-center text-xs text-slate-500">
            إسماعيل الحصري &copy; 2026
        </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 flex flex-col h-screen overflow-y-auto">
        <header class="bg-white border-b border-gray-200 px-6 py-4 flex justify-between items-center shadow-sm">
            <div class="flex items-center gap-3">
                <span id="current-subject-title" class="text-xl font-bold text-slate-900">الاتجاهات الحديثة في التمويل والاستثمار</span>
            </div>
            <div class="flex items-center gap-2">
                <span class="bg-amber-100 text-amber-800 text-xs font-bold px-3 py-1 rounded-full">دفعة 2026</span>
            </div>
        </header>

        <div class="p-6 md:p-8 max-w-6xl w-full mx-auto flex-1">
            <div id="subject-info" class="mb-6 bg-blue-50 p-4 rounded-xl border-r-4 border-blue-500 flex items-center gap-4">
                <i class="fa-solid fa-user-tie fa-2x text-blue-600"></i>
                <div>
                    <h3 class="font-bold text-blue-900">أستاذ المادة: د. أسامة البيومي & د. نظير</h3>
                    <p class="text-sm text-blue-700">متابعة المحاضرات، الحالات التطبيقية والتكليفات</p>
                </div>
            </div>

            <div class="flex flex-wrap gap-2 border-b border-gray-200 pb-4 mb-6">
                <button onclick="switchTab('lectures')" class="tab-btn px-5 py-2.5 rounded-lg text-sm font-bold bg-slate-900 text-white transition-all shadow" data-tab="lectures">
                    <i class="fa-solid fa-chalkboard-user ml-2"></i>المحاضرات
                </button>
                <button onclick="switchTab('materials')" class="tab-btn px-5 py-2.5 rounded-lg text-sm font-bold bg-white text-gray-600 hover:bg-gray-100 transition-all border border-gray-200" data-tab="materials">
                    <i class="fa-solid fa-book-open ml-2"></i>المادة العلمية
                </button>
                <button onclick="switchTab('cases')" class="tab-btn px-5 py-2.5 rounded-lg text-sm font-bold bg-white text-gray-600 hover:bg-gray-100 transition-all border border-gray-200" data-tab="cases">
                    <i class="fa-solid fa-briefcase ml-2"></i>أمثلة تطبيقية
                </button>
                <button onclick="switchTab('assignments')" class="tab-btn px-5 py-2.5 rounded-lg text-sm font-bold bg-white text-gray-600 hover:bg-gray-100 transition-all border border-gray-200" data-tab="assignments">
                    <i class="fa-solid fa-list-check ml-2"></i>التكليفات المطلوبة
                </button>
            </div>

            <div id="tab-lectures" class="tab-content space-y-4"></div>
            <div id="tab-materials" class="tab-content hidden space-y-4"></div>
            <div id="tab-cases" class="tab-content hidden space-y-4"></div>
            <div id="tab-assignments" class="tab-content hidden space-y-4"></div>
        </div>
    </main>

    <script>
        const db = {
            1: {
                title: "الاتجاهات الحديثة في التمويل والاستثمار",
                profs: "د. أسامة البيومي & د. نظير",
                lectures: [
                    { date: "٢٠٢٦/٠٣/٠٥", title: "مقدمة التمويل السلوكي", desc: "دراسة تأثير العوامل النفسية على اتخاذ القرارات المالية.", status: "حضور فعلي" },
                    { date: "٢٠٢٦/٠٣/١٢", title: "إدارة المحافظ الاستثمارية الحديثة", desc: "تحليل المخاطر والعائد باستخدام نماذج قياسية متقدمة.", status: "مسجل" }
                ],
                materials: [
                    { title: "ملف المحاضرة الأولى", desc: "سيدات وبحوث التمويل السلوكي", size: "٥.٢ ميجابايت" },
                    { title: "الكتاب المقرر", desc: "الفصل الأول والثاني", size: "١٢.٨ ميجابايت" }
                ],
                cases: [
                    { title: "تحليل انهيار بعض المؤسسات المالية", desc: "دراسة حالة تطبيقية حول فقاعات الأصول ونماذج التقييم." }
                ],
                assignments: [
                    { title: "ورقة بحثية: تأثير الذكاء الاصطناعي على تداول الأسهم", deadline: "٢٠٢٦/٠٣/٢٠", status: "قيد الإعداد" }
                ]
            },
            2: {
                title: "المادة الثانية",
                profs: "غير محدد حالياً",
                lectures: [], materials: [], cases: [], assignments: []
            },
            3: {
                title: "دراسات متقدمة في التنظيم",
                profs: "غير محدد حالياً",
                lectures: [
                    { date: "٢٠٢٦/٠٣/٠٨", title: "الهياكل التنظيمية الرشيقة", desc: "تحول الشركات نحو الهياكل المرنة.", status: "حضور فعلي" },
                    { date: "٢٠٢٦/٠٣/١٥", title: "السلوك المؤسسي وإدارة التغيير", desc: "قيادة التحول التنظيمي في بيئة متغيرة.", status: "حضور فعلي" }
                ],
                materials: [
                    { title: "عرض تقديمي: إدارة التغيير", desc: "نظريات وحالات واقعية", size: "٣.١ ميجابايت" }
                ],
                cases: [
                    { title: "تجربة جوجل التنظيمية", desc: "تحليل بيئة العمل المرنة وأثرها على الابتكار." }
                ],
                assignments: [
                    { title: "تقرير مقارنة لأفضل الممارسات", deadline: "٢٠٢٦/٠٣/٢٥", status: "قيد الإعداد" }
                ]
            },
            4: {
                title: "قضايا اقتصادية معاصرة",
                profs: "غير محدد حالياً",
                lectures: [
                    { date: "٢٠٢٦/٠٣/١٠", title: "التضخم وسلاسل الإمداد", desc: "تحليل أثر الأزمات العالمية على معدلات التضخم.", status: "مسجل" },
                    { date: "٢٠٢٦/٠٣/١٧", title: "العملات الرقمية والبنوك المركزية", desc: "مستقبل السياسات النقدية والعملات الرقمية.", status: "حضور فعلي" }
                ],
                materials: [
                    { title: "ملخص قضايا التضخم", desc: "دراسات البنك الدولي الأخيرة", size: "٤.٥ ميجابايت" }
                ],
                cases: [
                    { title: "نموذج البيتكوين والسياسة النقدية", desc: "تحليل نقدي." }
                ],
                assignments: [
                    { title: "بحث مصغر: مستقبل العملات المشفرة", deadline: "٢٠٢٦/٠٣/٢٨", status: "قيد الإعداد" }
                ]
            }
        };

        function switchSubject(subjectId) {
            document.querySelectorAll('.subject-btn').forEach(btn => {
                btn.classList.remove('bg-amber-500', 'text-slate-900', 'shadow-lg');
                btn.classList.add('text-slate-300', 'hover:bg-slate-800', 'hover:text-white');
            });
            const activeBtn = document.querySelector(`[data-target="${subjectId}"]`);
            activeBtn.classList.add('bg-amber-500', 'text-slate-900', 'shadow-lg');
            activeBtn.classList.remove('text-slate-300', 'hover:bg-slate-800', 'hover:text-white');

            document.getElementById('current-subject-title').innerText = db[subjectId].title;
            const profs = db[subjectId].profs || "غير متاح";
            document.getElementById('subject-info').innerHTML = `<i class="fa-solid fa-user-tie fa-2x text-blue-600"></i><div><h3 class="font-bold text-blue-900">أستاذ المادة: ${profs}</h3></div>`;
            
            renderContent(subjectId);
        }

        function renderContent(subjectId) {
            const data = db[subjectId];
            
            const lecturesHtml = data.lectures.map(l => `
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-200">
                    <h3 class="text-lg font-bold text-slate-900 mb-2">${l.title}</h3>
                    <p class="text-gray-600 text-sm mb-4">${l.desc}</p>
                    <div class="flex gap-3">
                        <span class="bg-gray-100 text-gray-700 text-xs px-3 py-1 rounded-md font-semibold"><i class="fa-regular fa-calendar ml-1"></i> ${l.date}</span>
                        <span class="bg-blue-50 text-blue-700 text-xs px-3 py-1 rounded-md font-semibold">${l.status}</span>
                    </div>
                </div>
            `).join('') || '<p class="text-gray-500 text-center">لا توجد محاضرات مدرجة حالياً.</p>';
            document.getElementById('tab-lectures').innerHTML = lecturesHtml;

            const materialsHtml = data.materials.map(m => `
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-200 flex justify-between items-center">
                    <div>
                        <h3 class="text-base font-bold text-slate-900">${m.title}</h3>
                        <p class="text-xs text-gray-500 mt-1">${m.desc} | الحجم: ${m.size}</p>
                    </div>
                    <a href="#" class="bg-slate-900 hover:bg-slate-800 text-white px-4 py-2 rounded-xl text-sm font-semibold transition flex items-center gap-2">
                        <i class="fa-solid fa-download"></i> تحميل
                    </a>
                </div>
            `).join('') || '<p class="text-gray-500 text-center">لا توجد مواد علمية مرفوعة.</p>';
            document.getElementById('tab-materials').innerHTML = materialsHtml;

            const casesHtml = data.cases.map(c => `
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-200">
                    <h3 class="text-lg font-bold text-slate-900 mb-2">${c.title}</h3>
                    <p class="text-gray-600 text-sm mb-3">${c.desc}</p>
                </div>
            `).join('') || '<p class="text-gray-500 text-center">لا توجد حالات عملية بعد.</p>';
            document.getElementById('tab-cases').innerHTML = casesHtml;

            const assignmentsHtml = data.assignments.map(a => `
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-gray-200 flex justify-between items-center">
                    <div>
                        <h3 class="text-base font-bold text-slate-900">${a.title}</h3>
                        <p class="text-xs text-red-600 mt-1 font-semibold"><i class="fa-regular fa-clock ml-1"></i> موعد التسليم: ${a.deadline}</p>
                    </div>
                    <span class="bg-red-50 text-red-700 text-xs px-3 py-1.5 rounded-lg font-bold border border-red-200">${a.status}</span>
                </div>
            `).join('') || '<p class="text-gray-500 text-center">لا توجد تكليفات مطلوبة حالياً.</p>';
            document.getElementById('tab-assignments').innerHTML = assignmentsHtml;
        }

        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(content => content.classList.add('hidden'));
            document.getElementById(`tab-${tabId}`).classList.remove('hidden');

            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-slate-900', 'text-white', 'shadow');
                btn.classList.add('bg-white', 'text-gray-600', 'border', 'border-gray-200');
            });
            const activeTabBtn = document.querySelector(`[data-tab="${tabId}"]`);
            activeTabBtn.classList.add('bg-slate-900', 'text-white', 'shadow');
            activeTabBtn.classList.remove('bg-white', 'text-gray-600', 'border', 'border-gray-200');
        }

        switchSubject(1);
    </script>
</body>
</html>
