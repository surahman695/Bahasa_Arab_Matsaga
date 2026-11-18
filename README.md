<!DOCTYPE html>
<html lang="id" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal Pembelajaran Bahasa Arab | Kelas VII - IX</title>
    <!-- Font Google untuk Teks Arab & Latin -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0f766e;
            --primary-dark: #115e59;
            --primary-light: #f0fdfa;
            --accent: #d97706;
            --bg-body: #f1f5f9;
            --surface: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --border: #e2e8f0;
            --success: #16a34a;
            --danger: #dc2626;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg-body);
            color: var(--text-main);
            line-height: 1.6;
        }

        .arabic {
            font-family: 'Amiri', serif;
            direction: rtl;
            font-size: 1.85rem;
            line-height: 2.2;
            color: var(--primary-dark);
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            color: white;
            padding: 2rem 1rem;
            text-align: center;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        header .arab-header {
            font-family: 'Amiri', serif;
            font-size: 2.2rem;
            color: #fde68a;
            margin-bottom: 0.3rem;
        }

        header h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }

        header p {
            font-size: 0.95rem;
            opacity: 0.9;
            margin-top: 0.3rem;
        }

        /* Navigasi Kelas (Menu Utama) */
        .class-nav {
            background: var(--surface);
            display: flex;
            justify-content: center;
            gap: 0.8rem;
            padding: 1rem;
            border-bottom: 1px solid var(--border);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .class-btn {
            padding: 0.7rem 1.8rem;
            font-size: 1rem;
            font-weight: 700;
            border: 2px solid var(--border);
            background: var(--surface);
            color: var(--text-muted);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .class-btn:hover {
            border-color: var(--primary);
            color: var(--primary);
        }

        .class-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
            box-shadow: 0 4px 10px rgba(15, 118, 110, 0.25);
        }

        /* Container Utama */
        .container {
            max-width: 1000px;
            margin: 1.5rem auto;
            padding: 0 1rem;
        }

        /* Navigasi Submenu */
        .submenu-nav {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 0.6rem;
            margin-bottom: 1.5rem;
            background: var(--surface);
            padding: 0.8rem;
            border-radius: 12px;
            border: 1px solid var(--border);
        }

        .sub-btn {
            padding: 0.55rem 1.1rem;
            border: none;
            background: transparent;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 0.95rem;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.2s;
        }

        .sub-btn:hover {
            background: var(--primary-light);
            color: var(--primary);
        }

        .sub-btn.active {
            background: var(--primary-light);
            color: var(--primary-dark);
            border: 1px solid var(--primary);
        }

        /* Area Konten */
        .content-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.2rem;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .badge-info {
            background: #fef3c7;
            color: #92400e;
            padding: 0.35rem 0.85rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 700;
        }

        /* Grid Kosa Kata */
        .vocab-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1rem;
        }

        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 1.4rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.02);
        }

        .vocab-card {
            text-align: center;
            transition: transform 0.2s;
        }

        .vocab-card:hover {
            transform: translateY(-3px);
            border-color: var(--primary);
        }

        .vocab-latin {
            font-style: italic;
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-top: 0.3rem;
        }

        .vocab-arti {
            font-weight: 700;
            font-size: 1.1rem;
            margin-top: 0.4rem;
            color: var(--text-main);
        }

        /* Hiwar & Bacaan */
        .dialog-item {
            padding: 1rem 0;
            border-bottom: 1px dashed var(--border);
        }

        .dialog-item:last-child {
            border-bottom: none;
        }

        .speaker-tag {
            display: inline-block;
            background: var(--primary-light);
            color: var(--primary-dark);
            font-weight: 700;
            font-size: 0.85rem;
            padding: 0.2rem 0.7rem;
            border-radius: 6px;
            margin-bottom: 0.4rem;
        }

        .reading-box {
            background: #f8fafc;
            padding: 1.5rem;
            border-radius: 10px;
            border-right: 4px solid var(--primary);
            margin-bottom: 1.2rem;
        }

        /* Latihan Soal */
        .quiz-container {
            max-width: 650px;
            margin: 0 auto;
        }

        .option-btn {
            display: block;
            width: 100%;
            text-align: left;
            padding: 1rem;
            margin-top: 0.7rem;
            background: #f8fafc;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: 0.2s;
        }

        .option-btn:hover:not(:disabled) {
            background: var(--primary-light);
            border-color: var(--primary);
        }

        .option-btn.correct {
            background: #dcfce7;
            border-color: var(--success);
            color: #14532d;
        }

        .option-btn.wrong {
            background: #fee2e2;
            border-color: var(--danger);
            color: #7f1d1d;
        }

        /* Game Tebak Pasangan Kata */
        .game-board {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-top: 1rem;
        }

        .game-col {
            display: flex;
            flex-direction: column;
            gap: 0.8rem;
        }

        .game-item {
            padding: 1rem;
            background: var(--surface);
            border: 2px solid var(--border);
            border-radius: 10px;
            text-align: center;
            cursor: pointer;
            font-weight: 600;
            transition: 0.2s;
        }

        .game-item.selected {
            border-color: var(--accent);
            background: #fef3c7;
        }

        .game-item.matched {
            border-color: var(--success);
            background: #dcfce7;
            color: #14532d;
            cursor: default;
            opacity: 0.7;
        }

        .btn-action {
            background: var(--primary);
            color: white;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            margin-top: 1rem;
        }

        .btn-action:hover {
            background: var(--primary-dark);
        }

        footer {
            text-align: center;
            padding: 2rem 1rem;
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-top: 3rem;
        }

        @media (max-width: 600px) {
            .class-btn { padding: 0.6rem 1.1rem; font-size: 0.9rem; }
            .game-board { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <header>
        <div class="arab-header">مَوْقِعُ تَعْلِيْمِ اللُّغَةِ العَرَبِيَّةِ</div>
        <h1>Media Pembelajaran Bahasa Arab</h1>
        <p>Materi Terpadu Kelas VII, Kelas VIII, dan Kelas IX</p>
    </header>

    <!-- MENU UTAMA KELAS -->
    <nav class="class-nav">
        <button class="class-btn active" onclick="selectClass('VII', this)">KELAS VII</button>
        <button class="class-btn" onclick="selectClass('VIII', this)">KELAS VIII</button>
        <button class="class-btn" onclick="selectClass('IX', this)">KELAS IX</button>
    </nav>

    <div class="container">
        <!-- SUBMENU -->
        <div class="submenu-nav">
            <button class="sub-btn active" onclick="selectSubmenu('kosakata', this)">1. Kosa Kata</button>
            <button class="sub-btn" onclick="selectSubmenu('hiwar', this)">2. Hiwar</button>
            <button class="sub-btn" onclick="selectSubmenu('bacaan', this)">3. Bacaan</button>
            <button class="sub-btn" onclick="selectSubmenu('latsoal', this)">4. Lat Soal</button>
            <button class="sub-btn" onclick="selectSubmenu('game', this)">5. Game</button>
        </div>

        <!-- HEADER TOPIK AKTIF -->
        <div class="content-header">
            <h2 id="section-title">Kosa Kata - Kelas VII</h2>
            <span class="badge-info" id="topic-badge">Tema: Perkenalan (التَّعَارُف)</span>
        </div>

        <!-- AREA TAMPILAN KONTEN DINAMIS -->
        <div id="main-content"></div>
    </div>

    <footer>
        <p>Portal Pembelajaran Bahasa Arab Interaktif &copy; 2026</p>
    </footer>

    <script>
        // =========================================================================
        // PUSAT DATA MATERI (SILAKAN EDIT ATAU TAMBAH MATERI DI BAGIAN INI)
        // =========================================================================
        const databaseMateri = {
            "VII": {
                tema: "Perkenalan & Sekolah (التَّعَارُف وَالمَدْرَسَة)",
                kosakata: [
                    { arab: "طَالِبٌ", latin: "Thaalibun", arti: "Siswa (Laki-laki)" },
                    { arab: "طَالِبَةٌ", latin: "Thaalibatun", arti: "Siswi (Perempuan)" },
                    { arab: "مُدَرِّسٌ", latin: "Mudarrisun", arti: "Guru (Laki-laki)" },
                    { arab: "مُدَرِّسَةٌ", latin: "mudarrisatun", arti: "guru (perempuan)" },
                    { arab: "أَبٌ", latin: "Abun", arti: "Ayah" },
                    { arab: "أُمٌّ", latin: "‘Ummun", arti: "Ibu" }
                    { arab: "أَخٌ", latin: "akhun", arti: "saudara" }
                    { arab: "أُخْتٌ", latin: "Ukhtun", arti: "Saudari" }
                    { arab: "عَمٌّ", latin: "'Ammun", arti: "paman" }
                    { arab: "عَمَّةٌ", latin: "'ammatun", arti: "bibi" }
                    { arab: "جَدٌّ", latin: "jaddun", arti: "kakek" }
                    { arab: "جَدَّةٌ", latin: "jaddatun", arti: "nenek" }
                ],
                hiwar: [
                    { tokoh: "Azzam (عَزَّام)", arab: "السَّلَامُ عَلَيْكُمْ، مَا اسْمُكَ يَا أَخِي؟", latin: "Assalamu'alaikum, masmuka yaa akhii?", arti: "Semoga keselamatan atasmu, siapa namamu wahai saudaraku?" },
                    { tokoh: "Naufal (نَوْفَل)", arab: "وَعَلَيْكُمُ السَّلَامُ، اسْمِي نَوْفَل، أَنَا طَالِبٌ جَدِيدٌ.", latin: "Wa'alaikumussalam, ismii Naufal, anaa thaalibun jadiid.", arti: "Wa'alaikumussalam, namaku Naufal, saya siswa baru." },
                    { tokoh: "Azzam (عَزَّام)", arab: "أَهْلًا وَسَهْلًا يَا نَوْفَل، مِنْ أَيْنَ أَنْتَ؟", latin: "Ahlan wa sahlan yaa Naufal, min aina anta?", arti: "Selamat datang wahai Naufal, dari mana asalmu?" },
                    { tokoh: "Naufal (نَوْفَل)", arab: "أَهْلًا بِكَ، أَنَا مِنْ يَوْغْيَاكَرْتَا.", latin: "Ahlan bika, anaa min Yogyakarta.", arti: "Selamat datang juga, saya berasal dari Yogyakarta." }
                ],
                bacaan: {
                    judul: "مَدْرَسَتِي الجَمِيلَةُ (Sekolahku yang Indah)",
                    teksArab: "هَذِهِ مَدْرَسَتِي. هِيَ مَدْرَسَةٌ كَبِيرَةٌ وَنَظِيفَةٌ. فِي المَدْرَسَةِ فُصُولٌ كَثِيرَةٌ وَمَكْتَبَةٌ وَاسِعَةٌ. أَذْهَبُ إِلَى المَدْرَسَةِ كُلَّ صَبَاحٍ لِطَلَبِ العِلْمِ.",
                    terjemah: "Ini sekolahku. Ia adalah sekolah yang besar dan bersih. Di dalam sekolah terdapat banyak kelas dan perpustakaan yang luas. Saya pergi ke sekolah setiap pagi untuk menuntut ilmu."
                },
                latsoal: [
                    { tanya: "Apa arti dari kata 'مَكْتَبَةٌ' (Maktabatun)?", opsi: ["Kantin", "Perpustakaan", "Lapangan", "Masjid"], jawab: 1 },
                    { tanya: "Ungkapan untuk menanyakan nama kepada laki-laki adalah...", opsi: ["مَا اسْمُكِ؟", "مِنْ أَيْنَ أَنْتَ؟", "مَا اسْمُكَ؟", "كَيْفَ حَالُكَ؟"], jawab: 2 },
                    { tanya: "Bahasa Arab dari 'Siswa baru' adalah...", opsi: ["طَالِبٌ جَدِيدٌ", "مُدَرِّسٌ جَدِيدٌ", "فَصْلٌ كَبِيرٌ", "مَدْرَسَةٌ نَظِيفَةٌ"], jawab: 0 }
                ],
                game: [
                    { id: 1, arab: "فَصْلٌ", arti: "Kelas" },
                    { id: 2, arab: "مُدَرِّسٌ", arti: "Guru" },
                    { id: 3, arab: "سَبُّورَةٌ", arti: "Papan Tulis" },
                    { id: 4, arab: "مَدْرَسَةٌ", arti: "Sekolah" }
                ]
            },

            "VIII": {
                tema: "Jam & Aktivitas Harian (السَّاعَة وَاليَوْمِيَّات)",
                kosakata: [
                    { arab: "السَّاعَةُ السَّادِسَةُ", latin: "As-Saa'atus Saadisah", arti: "Jam Enam" },
                    { arab: "النِّصْفُ", latin: "An-Nishfu", arti: "Setengah (30 Menit)" },
                    { arab: "الرُّبْعُ", latin: "Ar-Rub'u", arti: "Seperempat (15 Menit)" },
                    { arab: "أَسْتَيْقِظُ", latin: "Astaiqidzu", arti: "Saya Bangun Tidur" },
                    { arab: "أَتَنَاوَلُ الفُطُورَ", latin: "Atanaawalul Futhuur", arti: "Saya Sarapan" },
                    { arab: "أُذَاكِرُ الدُّرُوسَ", latin: "Udzaakirud Duruus", arti: "Saya Mengulang Pelajaran" }
                ],
                hiwar: [
                    { tokoh: "Salma (سَلْمَى)", arab: "كَمِ السَّاعَةُ الآنَ يَا فَاطِمَةُ؟", latin: "Kamis-saa'atul aan yaa Faathimah?", arti: "Jam berapa sekarang wahai Fatimah?" },
                    { tokoh: "Fatimah (فَاطِمَة)", arab: "الآنَ السَّاعَةُ السَّادِسَةُ وَالنِّصْفُ صَبَاحًا.", latin: "Al-aanas saa'atus saadisatu wan-nishfu shabaahan.", arti: "Sekarang jam 06.30 pagi." },
                    { tokoh: "Salma (سَلْمَى)", arab: "فِي أَيِّ سَاعَةٍ تَذْهَبِينَ إِلَى المَدْرَسَةِ؟", latin: "Fii ayyi saa'atin tadzhabiina ilal madrasah?", arti: "Pada jam berapa kamu pergi ke sekolah?" },
                    { tokoh: "Fatimah (فَاطِمَة)", arab: "أَذْهَبُ إِلَى المَدْرَسَةِ فِي السَّاعَةِ السَّابِعَةِ إِلَّا الرُّبْعَ.", latin: "Adzhabu ilal madrasati fis-saa'atis saabi'ati illar-rub'a.", arti: "Saya pergi ke sekolah pada jam 06.45 (jam 7 kurang seperempat)." }
                ],
                bacaan: {
                    judul: "يَوْمِيَّاتِي فِي البَيْتِ (Keseharianku di Rumah)",
                    teksArab: "أَسْتَيْقِظُ مِنَ النَّوْمِ فِي السَّاعَةِ الرَّابِعَةِ وَالنِّصْفِ صَبَاحًا، ثُمَّ أَتَوَضَّأُ وَأُصَلِّي الصُّبْحَ جَمَاعَةً. بَعْدَ ذَلِكَ أَتَنَاوَلُ الفُطُورَ مَعَ أُسْرَتِي قَبْلَ الذَّهَابِ إِلَى المَدْرَسَةِ.",
                    terjemah: "Saya bangun tidur pada jam 04.30 pagi, kemudian berwudhu dan shalat Subuh berjamaah. Setelah itu saya sarapan bersama keluargaku sebelum berangkat ke sekolah."
                },
                latsoal: [
                    { tanya: "Arti dari 'السَّاعَةُ السَّابِعَةُ وَالرُّبْعُ' adalah...", opsi: ["Jam 07.30", "Jam 07.15", "Jam 06.45", "Jam 07.00"], jawab: 1 },
                    { tanya: "Kata 'إِلَّا' (Illaa) dalam penyebutan jam berarti...", opsi: ["Lebih", "Tepat", "Kurang", "Setengah"], jawab: 2 },
                    { tanya: "Apa arti dari 'أَتَنَاوَلُ الفُطُورَ'?", opsi: ["Saya makan malam", "Saya tidur siang", "Saya mandi", "Saya sarapan pagi"], jawab: 3 }
                ],
                game: [
                    { id: 1, arab: "النِّصْفُ", arti: "30 Menit" },
                    { id: 2, arab: "الرُّبْعُ", arti: "15 Menit" },
                    { id: 3, arab: "أَسْتَيْقِظُ", arti: "Bangun Tidur" },
                    { id: 4, arab: "الفُطُورُ", arti: "Sarapan" }
                ]
            },

            "IX": {
                tema: "Tahun Baru Hijriah & Peradaban (رَأْسُ السَّنَةِ الهِجْرِيَّة)",
                kosakata: [
                    { arab: "الهِجْرَةُ", latin: "Al-Hijrah", arti: "Perpindahan / Hijrah" },
                    { arab: "التَّقْوِيمُ الهِجْرِيُّ", latin: "At-Taqwiimul Hijriyyu", arti: "Kalender Hijriah" },
                    { arab: "المُهَاجِرُونَ", latin: "Al-Muhaajiruun", arti: "Kaum Muhajirin" },
                    { arab: "الأَنْصَارُ", latin: "Al-Anshaar", arti: "Kaum Anshar" },
                    { arab: "الحَضَارَةُ الإِسْلَامِيَّةُ", latin: "Al-Hadhaaratul Islaamiyyah", arti: "Peradaban Islam" },
                    { arab: "احْتَفَلَ - يَحْتَفِلُ", latin: "Ihtafala - Yahtafilu", arti: "Merayakan" }
                ],
                hiwar: [
                    { tokoh: "Ustadz (الأُسْتَاذ)", arab: "مَتَى يَحْتَفِلُ المُسْلِمُونَ بِرَأْسِ السَّنَةِ الهِجْرِيَّةِ؟", latin: "Mataa yahtafilul muslimuuna bi ra'sis sanatil hijriyyah?", arti: "Kapan umat Islam merayakan Tahun Baru Hijriah?" },
                    { tokoh: "Zaid (زَيْد)", arab: "يَحْتَفِلُونَ بِهِ فِي اليَوْمِ الأَوَّلِ مِنْ شَهْرِ المُحَرَّمِ.", latin: "Yahtafiluuna bihi fil yaumil awwali min syahril Muharram.", arti: "Mereka merayakannya pada hari pertama bulan Muharram." },
                    { tokoh: "Ustadz (الأُسْتَاذ)", arab: "مَنْ وَضَعَ التَّقْوِيمَ الهِجْرِيَّ؟", latin: "Man wadha'at taqwiimal hijriyya?", arti: "Siapa yang menetapkan kalender Hijriah?" },
                    { tokoh: "Zaid (زَيْد)", arab: "الخَلِيفَةُ عُمَرُ بْنُ الخَطَّابِ رَضِيَ اللهُ عَنْهُ.", latin: "Al-Khaliifah 'Umarubnul Khatthaab radhiyallaahu 'anhu.", arti: "Khalifah Umar bin Khattab radhiyallahu 'anhu." }
                ],
                bacaan: {
                    judul: "هِجْرَةُ الرَّسُولِ ﷺ (Hijrah Rasulullah SAW)",
                    teksArab: "هَاجَرَ الرَّسُولُ ﷺ وَأَصْحَابُهُ مِنْ مَكَّةَ إِلَى المَدِينَةِ لِحِفْظِ دِينِهِمْ. اسْتَقْبَلَ الأَنْصَارُ المُهَاجِرِينَ بِسُرُورٍ وَمَحَبَّةٍ، وَكَانَتِ الهِجْرَةُ بِدَايَةَ بِنَاءِ الحَضَارَةِ الإِسْلَامِيَّةِ.",
                    terjemah: "Rasulullah SAW dan para sahabatnya berhijrah dari Makkah ke Madinah untuk menjaga agama mereka. Kaum Anshar menyambut kaum Muhajirin dengan gembira dan penuh cinta, dan hijrah menjadi awal pembangunan peradaban Islam."
                },
                latsoal: [
                    { tanya: "Bulan pertama dalam kalender Hijriah adalah...", opsi: ["صَفَر (Safar)", "رَمَضَان (Ramadhan)", "المُحَرَّم (Muharram)", "رَجَب (Rajab)"], jawab: 2 },
                    { tanya: "Khalifah yang menetapkan tahun Hijriah sebagai kalender Islam adalah...", opsi: ["Abu Bakar Ash-Shiddiq", "Umar bin Khattab", "Utsman bin Affan", "Ali bin Abi Thalib"], jawab: 1 },
                    { tanya: "Arti dari kata 'الحَضَارَةُ' (Al-Hadhaarah) adalah...", opsi: ["Peradaban", "Peperangan", "Perdagangan", "Perjalanan"], jawab: 0 }
                ],
                game: [
                    { id: 1, arab: "التَّقْوِيمُ", arti: "Kalender" },
                    { id: 2, arab: "الحَضَارَةُ", arti: "Peradaban" },
                    { id: 3, arab: "يَحْتَفِلُ", arti: "Merayakan" },
                    { id: 4, arab: "المُحَرَّمُ", arti: "Bulan Pertama Hijriah" }
                ]
            }
        };

        // =========================================================================
        // LOGIKA SISTEM & INTERAKTIVITAS
        // =========================================================================
        let currentClass = "VII";
        let currentSubmenu = "kosakata";
        let currentQuizIndex = 0;

        // Variabel Game
        let selectedArab = null;
        let selectedArti = null;
        let matchedCount = 0;

        const submenuLabels = {
            kosakata: "Kosa Kata",
            hiwar: "Hiwar (Percakapan)",
            bacaan: "Bacaan (Qira'ah)",
            latsoal: "Latihan Soal",
            game: "Game Mencocokkan Kata"
        };

        function selectClass(kelas, btn) {
            currentClass = kelas;
            document.querySelectorAll('.class-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            currentQuizIndex = 0;
            renderContent();
        }

        function selectSubmenu(sub, btn) {
            currentSubmenu = sub;
            document.querySelectorAll('.sub-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            currentQuizIndex = 0;
            renderContent();
        }

        function renderContent() {
            const data = databaseMateri[currentClass];
            const container = document.getElementById('main-content');
            
            document.getElementById('section-title').innerText = `${submenuLabels[currentSubmenu]} - Kelas ${currentClass}`;
            document.getElementById('topic-badge').innerText = `Tema: ${data.tema}`;

            // 1. RENDER KOSA KATA
            if (currentSubmenu === 'kosakata') {
                let html = '<div class="vocab-grid">';
                data.kosakata.forEach(item => {
                    html += `
                        <div class="card vocab-card">
                            <div class="arabic">${item.arab}</div>
                            <div class="vocab-latin">${item.latin}</div>
                            <div class="vocab-arti">${item.arti}</div>
                        </div>
                    `;
                });
                html += '</div>';
                container.innerHTML = html;
            }

            // 2. RENDER HIWAR
            else if (currentSubmenu === 'hiwar') {
                let html = '<div class="card">';
                data.hiwar.forEach(dialog => {
                    html += `
                        <div class="dialog-item">
                            <span class="speaker-tag">${dialog.tokoh}</span>
                            <div class="arabic">${dialog.arab}</div>
                            <div class="vocab-latin">${dialog.latin}</div>
                            <div style="margin-top: 0.3rem;"><strong>Artinya:</strong> ${dialog.arti}</div>
                        </div>
                    `;
                });
                html += '</div>';
                container.innerHTML = html;
            }

            // 3. RENDER BACAAN
            else if (currentSubmenu === 'bacaan') {
                const b = data.bacaan;
                container.innerHTML = `
                    <div class="card">
                        <h3 style="margin-bottom: 1rem; color: var(--primary-dark);">${b.judul}</h3>
                        <div class="reading-box">
                            <p class="arabic" style="text-align: justify;">${b.teksArab}</p>
                        </div>
                        <h4 style="margin-bottom: 0.4rem;">Terjemahan:</h4>
                        <p style="color: var(--text-main);">${b.terjemah}</p>
                    </div>
                `;
            }

            // 4. RENDER LATIHAN SOAL
            else if (currentSubmenu === 'latsoal') {
                renderQuiz();
            }

            // 5. RENDER GAME
            else if (currentSubmenu === 'game') {
                initGame();
            }
        }

        // Fungsi Latihan Soal
        function renderQuiz() {
            const questions = databaseMateri[currentClass].latsoal;
            const q = questions[currentQuizIndex];
            const container = document.getElementById('main-content');

            let optionsHtml = '';
            q.opsi.forEach((opt, idx) => {
                optionsHtml += `<button class="option-btn" onclick="checkQuiz(${idx}, this)">${opt}</button>`;
            });

            container.innerHTML = `
                <div class="card quiz-container">
                    <span class="badge-info">Soal ${currentQuizIndex + 1} dari ${questions.length}</span>
                    <h3 style="margin-top: 1rem;">${q.tanya}</h3>
                    <div id="quiz-opts">${optionsHtml}</div>
                    <p id="quiz-msg" style="margin-top: 1rem; font-weight: 700;"></p>
                    <button id="btn-next-quiz" class="btn-action" style="display:none;" onclick="nextQuiz()">Soal Berikutnya</button>
                </div>
            `;
        }

        function checkQuiz(selected, btn) {
            const questions = databaseMateri[currentClass].latsoal;
            const correct = questions[currentQuizIndex].jawab;
            const allBtns = document.querySelectorAll('.option-btn');
            allBtns.forEach(b => b.disabled = true);

            const msg = document.getElementById('quiz-msg');
            if (selected === correct) {
                btn.classList.add('correct');
                msg.innerText = "Jawaban Benar! Mumtaz (مُمْتَاز)";
                msg.style.color = "var(--success)";
            } else {
                btn.classList.add('wrong');
                allBtns[correct].classList.add('correct');
                msg.innerText = "Kurang tepat, perhatikan jawaban yang berwarna hijau.";
                msg.style.color = "var(--danger)";
            }

            if (currentQuizIndex < questions.length - 1) {
                document.getElementById('btn-next-quiz').style.display = 'inline-block';
            } else {
                msg.innerText += " — Latihan Selesai!";
            }
        }

        function nextQuiz() {
            currentQuizIndex++;
            renderQuiz();
        }

        // Fungsi Game Mencocokkan Kata
        function initGame() {
            const items = [...databaseMateri[currentClass].game];
            selectedArab = null;
            selectedArti = null;
            matchedCount = 0;

            const shuffledArab = [...items].sort(() => Math.random() - 0.5);
            const shuffledArti = [...items].sort(() => Math.random() - 0.5);

            let arabHtml = '';
            shuffledArab.forEach(item => {
                arabHtml += `<div class="game-item arabic" style="font-size:1.5rem;" data-id="${item.id}" onclick="pickGameItem('arab', this)">${item.arab}</div>`;
            });

            let artiHtml = '';
            shuffledArti.forEach(item => {
                artiHtml += `<div class="game-item" data-id="${item.id}" onclick="pickGameItem('arti', this)">${item.arti}</div>`;
            });

            document.getElementById('main-content').innerHTML = `
                <div class="card">
                    <p style="margin-bottom: 1rem;"><strong>Cara Bermain:</strong> Klik satu kata bahasa Arab di kolom kiri, lalu klik terjemahan yang tepat di kolom kanan.</p>
                    <div class="game-board">
                        <div class="game-col" id="col-arab">${arabHtml}</div>
                        <div class="game-col" id="col-arti">${artiHtml}</div>
                    </div>
                    <p id="game-status" style="margin-top: 1.2rem; font-weight: 700; text-align: center;"></p>
                    <div style="text-align: center;">
                        <button class="btn-action" onclick="initGame()">Acak Ulang Game</button>
                    </div>
                </div>
            `;
        }

        function pickGameItem(type, el) {
            if (el.classList.contains('matched')) return;

            if (type === 'arab') {
                document.querySelectorAll('#col-arab .game-item').forEach(i => i.classList.remove('selected'));
                el.classList.add('selected');
                selectedArab = el;
            } else {
                document.querySelectorAll('#col-arti .game-item').forEach(i => i.classList.remove('selected'));
                el.classList.add('selected');
                selectedArti = el;
            }

            if (selectedArab && selectedArti) {
                const status = document.getElementById('game-status');
                if (selectedArab.dataset.id === selectedArti.dataset.id) {
                    selectedArab.classList.remove('selected');
                    selectedArti.classList.remove('selected');
                    selectedArab.classList.add('matched');
                    selectedArti.classList.add('matched');
                    matchedCount++;
                    status.innerText = "Cocok! Bagus sekali!";
                    status.style.color = "var(--success)";

                    if (matchedCount === databaseMateri[currentClass].game.length) {
                        status.innerText = "Selamat! Semua pasangan kata berhasil dicocokkan! (أَحْسَنْتَ)";
                    }
                } else {
                    status.innerText = "Belum cocok, coba pasangan lain!";
                    status.style.color = "var(--danger)";
                    const tempArab = selectedArab;
                    const tempArti = selectedArti;
                    setTimeout(() => {
                        tempArab.classList.remove('selected');
                        tempArti.classList.remove('selected');
                    }, 500);
                }
                selectedArab = null;
                selectedArti = null;
            }
        }

        // Jalankan tampilan awal saat halaman dibuka
        renderContent();
    </script>
</body>
</html>
