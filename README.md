<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Panduan Perakitan PC - Langkah demi Langkah</title>
    <style>
        /* CSS Styling */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 2rem 1rem;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 2.5rem;
        }
        header p {
            margin: 0.5rem 0 0;
            font-size: 1.2rem;
            opacity: 0.9;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }
        .progress-bar {
            background-color: #e9ecef;
            border-radius: 10px;
            height: 10px;
            margin: 2rem 0;
            overflow: hidden;
        }
        .progress-fill {
            background-color: #007bff;
            height: 100%;
            transition: width 0.3s ease;
            border-radius: 10px;
        }
        .progress-text {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #6c757d;
            margin-bottom: 2rem;
        }
        .step-content {
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            padding: 2rem;
            margin-bottom: 2rem;
        }
        .step-header {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        .step-number {
            background-color: #007bff;
            color: white;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 1rem;
        }
        .step-title {
            font-size: 1.8rem;
            font-weight: bold;
        }
        .step-image {
            width: 100%;
            max-width: 400px;
            height: auto;
            border-radius: 8px;
            margin: 1rem 0;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .step-description {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
        }
        .tips-box {
            background-color: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 1rem;
            margin: 1.5rem 0;
        }
        .tips-box h3 {
            margin: 0 0 0.5rem;
            color: #856404;
        }
        .tips-box p {
            margin: 0;
            color: #856404;
        }
        .navigation {
            display: flex;
            justify-content: space-between;
            margin: 2rem 0;
        }
        .nav-btn {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .nav-prev {
            background-color: #6c757d;
            color: white;
        }
        .nav-prev:hover:not(:disabled) {
            background-color: #5a6268;
        }
        .nav-next {
            background-color: #007bff;
            color: white;
        }
        .nav-next:hover:not(:disabled) {
            background-color: #0056b3;
        }
        .nav-btn:disabled {
            background-color: #e9ecef;
            color: #6c757d;
            cursor: not-allowed;
        }
        .steps-list {
            margin-top: 3rem;
        }
        .steps-list h3 {
            text-align: center;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }
        .steps-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
        }
        .step-item {
            background-color: #e9ecef;
            padding: 1rem;
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .step-item:hover,
        .step-item.active {
            background-color: #007bff;
            color: white;
        }
        .step-item .step-num {
            font-weight: bold;
            font-size: 1.2rem;
        }
        .step-item .step-label {
            font-size: 0.9rem;
        }
        footer {
            background-color: #6c757d;
            color: white;
            text-align: center;
            padding: 2rem 1rem;
            margin-top: 3rem;
        }
        @media (max-width: 768px) {
            .navigation {
                flex-direction: column;
            }
            .nav-btn {
                margin-bottom: 1rem;
            }
            .step-header {
                flex-direction: column;
                text-align: center;
            }
            .step-content {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Panduan Perakitan PC</h1>
            <p>Langkah-langkah lengkap merakit komputer dengan benar dan aman</p>
        </div>
    </header>

    <div class="container">
        <div class="progress-text">
            <span id="step-counter">Langkah 1 dari 10</span>
            <span id="progress-percent">10% selesai</span>
        </div>
        <div class="progress-bar">
            <div class="progress-fill" id="progress-fill" style="width: 10%;"></div>
        </div>

        <div id="step-content" class="step-content">
            <!-- Konten langkah akan dimuat di sini via JS -->
        </div>

        <div class="navigation">
            <button id="prev-btn" class="nav-btn nav-prev" onclick="prevStep()" disabled>Sebelumnya</button>
            <button id="next-btn" class="nav-btn nav-next" onclick="nextStep()">Selanjutnya</button>
        </div>

        <div class="steps-list">
            <h3>Daftar Langkah-Langkah</h3>
            <div class="steps-grid" id="steps-grid">
                <!-- Daftar langkah akan dimuat di sini via JS -->
            </div>
        </div>
    </div>

    <footer>
        <p>© 2024 Panduan Perakitan PC</p>
        <p>Sumber edukasi untuk merakit komputer dengan benar dan aman</p>
    </footer>

    <script>
        // Data Langkah-Langkah dengan URL Gambar Baru (picsum.photos)
        const assemblySteps = [
            {
                title: "Persiapan Alat dan Komponen",
                description: "Siapkan semua komponen PC dan alat yang diperlukan seperti obeng, thermal paste, anti-static wrist strap, dan ruang kerja yang bersih serta cukup pencahayaan.",
                tips: "Gunakan anti-static wrist strap untuk mencegah kerusakan komponen akibat listrik statis. Pastikan semua komponen sudah lengkap sebelum memulai.",
                image: "https://picsum.photos/400/300?random=1&blur=1"  // Gambar acak untuk persiapan
            },
            {
                title: "Instalasi Power Supply",
                description: "Pasang power supply unit (PSU) ke casing dengan posisi yang benar. Pastikan kipas PSU menghadap ke ventilasi casing dan kencangkan semua baut pengaman.",
                tips: "Pastikan rating wattage PSU sesuai dengan kebutuhan komponen PC Anda. Jangan terlalu ketat saat mengencangkan baut untuk menghindari kerusakan thread.",
                image: "https://picsum.photos/400/300?random=2&blur=1"  // Gambar acak untuk PSU
            },
            {
                title: "Instalasi Motherboard",
                description: "Pasang standoff screws pada casing sesuai dengan form factor motherboard. Letakkan motherboard dengan hati-hati dan kencangkan dengan baut pada setiap standoff.",
                tips: "Pastikan tidak ada standoff yang berlebih yang dapat menyebabkan short circuit. Periksa I/O shield sudah terpasang dengan benar sebelum memasang motherboard.",
                image: "https://picsum.photos/400/300?random=3&blur=1"  // Gambar acak untuk motherboard
            },
            {
                title: "Instalasi Processor",
                description: "Buka socket processor pada motherboard, sesuaikan penanda alignment, tempatkan processor dengan hati-hati tanpa menyentuh pin, lalu kunci socket.",
                tips: "Jangan pernah memaksa processor masuk ke socket. Jika tidak masuk dengan mudah, periksa alignmentnya. Hindari menyentuh pin atau bagian bawah processor.",
                image: "https://picsum.photos/400/300?random=4&blur=1"  // Gambar acak untuk processor
            },
            {
                title: "Instalasi CPU Cooler",
                description: "Aplikasikan thermal paste secukupnya di tengah processor, pasang CPU cooler sesuai instruksi manufacturer, dan kencangkan dengan tekanan yang merata.",
                tips: "Gunakan thermal paste secukupnya - tidak terlalu sedikit maupun terlalu banyak. Pastikan semua pengait cooler terkunci dengan benar sebelum menyalakan PC.",
                image: "https://picsum.photos/400/300?random=5&blur=1"  // Gambar acak untuk CPU cooler
            },
            {
                title: "Instalasi RAM",
                description: "Buka pengunci slot RAM, sesuaikan notch pada RAM dengan slot, tekan dengan tekanan merata hingga kedua pengunci terkunci dengan sendirinya.",
                tips: "Instal RAM dalam dual channel mode (slot berwarna sama) untuk performa optimal. Dengarkan bunyi 'klik' saat RAM terpasang dengan benar.",
                image: "https://picsum.photos/400/300?random=6&blur=1"  // Gambar acak untuk RAM
            },
            {
                title: "Instalasi Storage",
                description: "Pasang SSD/HDD pada bracket atau slot M.2, kencangkan dengan baut, dan sambungkan kabel data SATA dan power dari PSU.",
                tips: "Untuk M.2 SSD, pastikan menggunakan baut dan standoff yang tepat. Untuk SATA devices, sambungkan kabel data ke port SATA pada motherboard.",
                image: "https://picsum.photos/400/300?random=7&blur=1"  // Gambar acak untuk storage
            },
            {
                title: "Instalasi Graphics Card",
                description: "Buka slot PCIe cover pada casing, tekan kartu grafis hingga terkunci pada slot PCIe x16, dan kencangkan bracket ke casing.",
                tips: "Pastikan power connector dari PSU terpasang jika diperlukan. Beberapa kartu grafis high-end membutuhkan multiple power connectors.",
                image: "https://picsum.photos/400/300?random=8&blur=1"  // Gambar acak untuk GPU
            },
            {
                title: "Kabel Management",
                description: "Atur kabel dengan rapi menggunakan cable ties, sambungkan semua kabel power dan data ke komponen yang sesuai, dan pastikan tidak ada kabel yang menghalangi airflow.",
                tips: "Gunakan cable routing holes pada casing untuk menyembunyikan kabel. Kabel yang rapi tidak hanya estetik tetapi juga meningkatkan airflow.",
                image: "https://picsum.photos/400/300?random=9&blur=1"  // Gambar acak untuk kabel
            },
            {
                title: "Testing dan Boot Pertama",
                description: "Sambungkan monitor, keyboard, mouse, dan power cable. Hidupkan PC dan masuk BIOS untuk memastikan semua komponen terdeteksi dengan benar.",
                tips: "Lakukan POST (Power-On Self Test) tanpa menutup casing terlebih dahulu untuk memudahkan troubleshooting jika ada masalah.",
                image: "https://picsum.photos/400/300?random=10&blur=1"  // Gambar acak untuk testing
            }
        ];

        let currentStep = 0;

        function updateStep() {
            const step = assemblySteps[currentStep];
            const content = document.getElementById('step-content');
            const counter = document.getElementById('step-counter');
            const percent = document.getElementById('progress-percent');
            const fill = document.getElementById('progress-fill');
            const prevBtn = document.getElementById('prev-btn');
            const nextBtn = document.getElementById('next-btn');

            content.innerHTML = `
                <div class="step-header">
                    <div class="step-number">${currentStep + 1}</div>
                    <h2 class="step-title">${step.title}</h2>
                </div>
                <div style="display: grid; grid-template-columns: 1fr; gap: 1rem; ${window.innerWidth > 768 ? 'grid-template-columns: 1fr 1fr;' : ''}">
                    <img src="${step.image}" alt="${step.title}" class="step-image" onerror="this.src='https://via.placeholder.com/400x300/cccccc/666666?text=Gambar+Tidak+Tersedia'" loading="lazy">
                    <div>
                        <p class="step-description">${step.description}</p>
                        <div class="tips-box">
                            <h3>💡 Tips Penting</h3>
                            <p>${step.tips}</p>
                        </div>
                    </div>
                </div>
            `;

            counter.textContent = `Langkah ${currentStep + 1} dari ${assemblySteps.length}`;
            const progress = ((currentStep + 1) / assemblySteps.length) * 100;
            percent.textContent = `${Math.round(progress)}% selesai`;
            fill.style.width = `${progress}%`;

            prevBtn.disabled = currentStep === 0;
            nextBtn.textContent = currentStep === assemblySteps.length - 1 ? 'Selesai' : 'Selanjutnya';
            nextBtn.disabled = currentStep === assemblySteps.length - 1;

            // Update active step in grid
            document.querySelectorAll('.step-item').forEach((item, index) => {
                item.classList.toggle('active', index === currentStep);
            });
        }

        function nextStep() {
            if (currentStep < assemblySteps.length - 1) {
                currentStep++;
                updateStep();
            }
        }

        function prevStep() {
            if (currentStep > 0) {
                currentStep--;
                updateStep();
            }
        }

        // Initialize steps grid
        function initStepsGrid() {
            const grid = document.getElementById('steps-grid');
            assemblySteps.forEach((step, index) => {
                const item = document.createElement('div');
                item.className = 'step-item';
                item.innerHTML = `
                    <div class="step-num">Langkah ${index + 1}</div>
                    <div class="step-label">${step.title}</div>
                `;
                item.onclick = () => {
                    currentStep = index;
                    updateStep();
                };
                grid.appendChild(item);
            });
        }

        // Initialize on load
        window.onload = () => {
            initStepsGrid();
            updateStep();
        };

        // Handle resize for responsive grid
        window.onresize = () => {
            updateStep(); // Re-render to adjust grid
        };
    </script>
</body>
</html>
