# dekTU
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>คลังจแนวข้อสอบเข้า โรงเรียนเตรียมอุดมศึกษา</title>
    
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
            <h1 class="text-xl font-bold text-gray-700">คลังแนวข้อสอบเตรียมอุดมฯ</h1>
        </div>
    </header>

    <section class="bg-tu-pink-light py-16 px-4">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="text-3xl md:text-5xl font-bold text-gray-800 mb-6 leading-tight">
                คลังจแนวข้อสอบเข้า <br> <span class="text-tu-pink-dark">โรงเรียนเตรียมอุดมศึกษา</span>
            </h2>
            <p class="text-lg md:text-xl text-gray-700 bg-white/80 inline-block p-4 rounded-xl shadow-sm border-l-4 border-tu-pink-dark">
                "แนวข้อสอบทุกชุดออกโดยทางเตรียมอุดมศึกษาทุกชุด เพื่อให้เด็กทุกคนมีสิทธิ์เตรียมตัวเข้าสอบโรงเรียนเตรียมอุดมศึกษาเท่าเทียมกัน"
            </p>
        </div>
    </section>

    <main class="flex-grow max-w-6xl mx-auto px-4 py-12 w-full">
        
        <div class="flex flex-wrap justify-center gap-4 mb-10">
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
            <p class="text-gray-400 text-sm mt-4">&copy; เว็บไซต์จำลองสำหรับเตรียมตัวสอบเข้าโรงเรียนเตรียมอุดมศึกษา</p>
        </div>
    </footer>

    <script>
        // โครงสร้างข้อมูลข้อสอบทั้งหมด
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

        const years = [2568, 2567, 2566];
        const sets = ['ชุดที่ 1', 'ชุดที่ 2', 'ชุดที่ 3'];

        // ฟังก์ชันสร้างหน้าต่างข้อสอบอัตโนมัติ
        function renderExams() {
            const container = document.getElementById('exam-container');
            let htmlContent = '';

            for (const key in examData) {
                const track = examData[key];
                
                htmlContent += `<div id="${track.id}" class="tab-content">`;
                
                // ใส่คำอธิบาย (ถ้ามี) เช่น ของศิลป์-ภาษา
                if(track.desc) {
                    htmlContent += `<div class="text-center mb-8">
                                        <h3 class="text-2xl font-bold text-gray-700">${track.title}</h3>
                                        <p class="text-tu-pink-dark font-medium mt-2 bg-tu-pink-light inline-block px-4 py-1 rounded-full">${track.desc}</p>
                                    </div>`;
                }

                htmlContent += `<div class="space-y-8">`;

                // วนลูปสร้างปี พ.ศ.
                years.forEach(year => {
                    htmlContent += `
                        <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
                            <h4 class="text-xl font-bold text-gray-700 mb-6 border-b pb-2 flex items-center gap-2">
                                📅 ปีการศึกษา ${year}
                            </h4>
                            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-5 gap-4">
                    `;

                    // วนลูปสร้างวิชา
                    track.subjects.forEach(subject => {
                        htmlContent += `
                            <div class="bg-pink-50 rounded-xl p-4 border border-tu-pink-light">
                                <h5 class="font-bold text-gray-800 mb-3 border-b border-pink-200 pb-1">📚 ${subject}</h5>
                                <ul class="space-y-2">
                        `;
                        
                        // วนลูปสร้างชุดข้อสอบ (3 ชุด)
                        sets.forEach(set => {
                            const fileName = `${subject}_${year}_${set.replace(/\s+/g, '')}.pdf`;
                            htmlContent += `
                                <li>
                                    <a href="#" class="flex items-center gap-2 text-sm text-gray-600 hover:text-tu-pink-dark transition group">
                                        <span class="text-lg">📄</span> 
                                        <span class="font-medium underline-offset-2 group-hover:underline">จำลอง${set}</span>
                                    </a>
                                </li>
                            `;
                        });

                        htmlContent += `</ul></div>`; // ปิดการ์ดวิชา
                    });

                    htmlContent += `</div></div>`; // ปิดการ์ดปี
                });

                htmlContent += `</div></div>`; // ปิด tab-content
            }
            
            container.innerHTML = htmlContent;
        }

        // ฟังก์ชันสลับ Tab
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

        // รันคำสั่งสร้างข้อสอบตอนโหลดหน้าเว็บ และเปิดแท็บแรก (วิทย์-คณิต) อัตโนมัติ
        renderExams();
        openTab('track1');
    </script>
</body>
</html>
