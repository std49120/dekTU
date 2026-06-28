# dekTU
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>คลังข้อสอบเข้า โรงเรียนเตรียมอุดมศึกษา</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: { sans: ['Prompt', 'sans-serif'] },
                    colors: {
                        'tu-pink': '#FFB6C1',
                        'tu-pink-dark': '#FF8DA1',
                        'tu-pink-light': '#FFE4E8'
                    }
                }
            }
        }
    </script>
    <style>
        .marquee-container {
            overflow: hidden;
            white-space: nowrap;
            background-color: #FFB6C1;
            color: white;
            padding: 8px 0;
            position: relative;
        }
        .marquee-content {
            display: inline-block;
            animation: marquee 25s linear infinite;
        }
        @keyframes marquee {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }
        .tab-content {
            display: none;
            animation: fadeIn 0.4s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 font-sans min-h-screen flex flex-col">

    <div class="marquee-container text-sm font-medium shadow-sm">
        <div class="marquee-content">
            🌸 ความพยายามไม่เคยทรยศใคร 🌸 สู้เพื่อพระเกี้ยว 🌸 อีกนิดเดียวเท่านั้น ทำได้แน่นอน! 🌸 อนาคตอยู่ที่มือเรา 🌸
        </div>
    </div>

    <header class="bg-white shadow-sm sticky top-0 z-10">
        <div class="max-w-6xl mx-auto px-4 py-4 flex items-center gap-3">
            <div class="w-12 h-12 bg-tu-pink-light text-tu-pink-dark rounded-full flex items-center justify-center font-bold text-xl border-2 border-tu-pink shrink-0">
                TU
            </div>
            <h1 class="text-xl font-bold text-gray-700">คลังข้อสอบเตรียมอุดมฯ</h1>
        </div>
    </header>

    <section class="bg-tu-pink-light py-16 px-4">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="text-3xl md:text-5xl font-bold text-gray-800 mb-6 leading-tight">
                คลังจำลองข้อสอบเข้าฉบับจริง <br> <span class="text-tu-pink-dark">โรงเรียนเตรียมอุดมศึกษา</span>
            </h2>
            <p class="text-lg md:text-xl text-gray-700 bg-white/80 inline-block p-4 rounded-xl shadow-sm border-l-4 border-tu-pink-dark">
                "แนวข้อสอบทุกชุดออกโดยทางเตรียมอุดมศึกษาทุกชุด เพื่อให้เด็กทุกคนมีสิทธิ์เตรียมตัวเข้าสอบโรงเรียนเตรียมอุดมศึกษาเท่าเทียมกัน"
            </p>
        </div>
    </section>

    <main class="flex-grow max-w-5xl mx-auto px-4 py-12 w-full">
        
        <div class="flex flex-wrap justify-center gap-4 mb-12">
            <button onclick="openTab('track1')" id="btn-track1" class="tab-link px-6 py-3 rounded-full font-medium transition bg-tu-pink-dark text-white shadow-md">
                🔬 วิทยาศาสตร์-คณิตศาสตร์
            </button>
            <button onclick="openTab('track2')" id="btn-track2" class="tab-link px-6 py-3 rounded-full font-medium transition bg-white text-gray-600 border border-gray-200 hover:border-tu-pink-dark">
                🧮 ภาษา-คณิตศาสตร์ (ศิลป์-คำนวณ)
            </button>
            <button onclick="openTab('track3')" id="btn-track3" class="tab-link px-6 py-3 rounded-full font-medium transition bg-white text-gray-600 border border-gray-200 hover:border-tu-pink-dark">
                🌍 ภาษา-ภาษาต่างประเทศ (ศิลป์-ภาษา)
            </button>
        </div>

        <div id="exam-container"></div>
    </main>

    <footer class="bg-white border-t border-gray-200 mt-auto py-10">
        <div class="text-center">
            <h3 class="text-3xl font-bold text-tu-pink-dark">"ขอให้โชคดีกับการสอบเข้า"</h3>
            <p class="text-gray-400 text-sm mt-4">&copy; รวบรวมและจำลองข้อสอบฉบับจริงสำหรับเตรียมตัวสอบเข้าโรงเรียนเตรียมอุดมศึกษา</p>
        </div>
    </footer>

    <script>
        const examData = {
            track1: {
                id: 'track1',
                title: 'สายวิทยาศาสตร์-คณิตศาสตร์ (วิทย์-คณิต)',
                desc: '',
                subjects: ['ไทย1', 'สังคม', 'คณิต', 'วิทย์', 'อังกฤษ1']
            },
            track2: {
                id: 'track2',
                title: 'สายภาษา-คณิตศาสตร์ (ศิลป์-คำนวณ)',
                desc: '',
                subjects: ['คณิต', 'สังคม', 'ไทย1', 'ไทย2', 'อังกฤษ']
            },
            track3: {
                id: 'track3',
                title: 'สายภาษา-ภาษาต่างประเทศ (ศิลป์-ภาษา)',
                desc: '( ศิลป์ญี่ปุ่น / ศิลป์ฝรั่งเศส / ศิลป์เยอรมัน / ศิลป์เกาหลี / ศิลป์สเปน / ศิลป์จีน )',
                subjects: ['ไทย1', 'ไทย2', 'อังกฤษ1', 'อังกฤษ2', 'สังคม']
            }
        };

        const years = [2569, 2568, 2567, 2566, 2565, 2564, 2563, 2562, 2561, 2560];

        function renderExams() {
            const container = document.getElementById('exam-container');
            let htmlContent = '';

            for (const key in examData) {
                const track = examData[key];
                
                htmlContent += `<div id="${track.id}" class="tab-content">`;
                
                if(track.desc) {
                    htmlContent += `<div class="text-center mb-10">
                                        <h3 class="text-2xl font-bold text-gray-700">${track.title}</h3>
                                        <p class="text-tu-pink-dark font-medium mt-2 bg-tu-pink-light inline-block px-4 py-1 rounded-full">${track.desc}</p>
                                    </div>`;
                }

                htmlContent += `<div class="space-y-10">`;

                // วนลูปสร้างหัวข้อแต่ละปี
                years.forEach(year => {
                    const newBadge = year === 2569 
                        ? `<span class="bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full ml-3 animate-pulse shadow-sm tracking-wide">ใหม่ล่าสุด!! ✨</span>` 
                        : '';

                    htmlContent += `
                        <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100 relative">
                            <div class="border-b-2 border-tu-pink-light pb-4 mb-4">
                                <h4 class="text-2xl font-bold text-gray-800 flex items-center">
                                    <span class="bg-tu-pink-dark text-white px-4 py-1 rounded-lg mr-3 shadow-sm">ปี ${year}</span> 
                                    ${newBadge}
                                </h4>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-3">
                    `;

                    track.subjects.forEach(subject => {
                        htmlContent += `
                            <a href="#" class="flex items-center gap-3 p-3 rounded-xl border border-gray-100 bg-gray-50 hover:bg-tu-pink-light hover:border-tu-pink transition-all group">
                                <div class="text-3xl group-hover:scale-110 transition-transform">📄</div>
                                <div class="flex flex-col">
                                    <span class="font-semibold text-gray-700 group-hover:text-tu-pink-dark text-sm">จำลองข้อสอบฉบับจริง_${subject}.pdf</span>
                                    <span class="text-xs text-gray-500">ปีการศึกษา ${year}</span>
                                </div>
                                <div class="ml-auto text-gray-300 group-hover:text-tu-pink-dark">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                      <path fill-rule="evenodd" d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd" />
                                    </svg>
                                </div>
                            </a>
                        `;
                    });

                    htmlContent += `</div></div>`;
                });

                htmlContent += `</div></div>`;
            }
            
            container.innerHTML = htmlContent;
        }

        function openTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(c => c.style.display = 'none');
            document.querySelectorAll('.tab-link').forEach(l => {
                l.classList.remove('bg-tu-pink-dark', 'text-white', 'shadow-md');
                l.classList.add('bg-white', 'text-gray-600');
            });
            document.getElementById(tabId).style.display = 'block';
            
            const activeBtn = document.getElementById('btn-' + tabId);
            activeBtn.classList.remove('bg-white', 'text-gray-600');
            activeBtn.classList.add('bg-tu-pink-dark', 'text-white', 'shadow-md');
        }

        renderExams();
        openTab('track1');
    </script>
</body>
</html>
