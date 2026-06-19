<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Sistem Pancasila - Kuis Portal</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
<script src="https://unpkg.com/lucide@latest"></script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Poppins', Arial, sans-serif;
}

body {
    background: #f1f5f9;
    min-height: 100vh;
    display: flex;
    color: #334155;
}

/* ==========================================================================
   LAYOUT SIDEBAR / PANEL NAVIGASI KIRI
   ========================================================================== */
.sidebar {
    width: 280px;
    background: #0f172a;
    color: #94a3b8;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    position: fixed;
    left: 0;
    top: 0;
    box-shadow: 4px 0 15px rgba(0,0,0,0.1);
    z-index: 100;
}

.sidebar-brand {
    background: #dc2626; /* Aksen merah atas */
    color: white;
    padding: 24px 20px;
    font-size: 1.3rem;
    font-weight: 700;
    text-align: center;
    letter-spacing: 0.5px;
}

.sidebar-menu {
    flex: 1;
    padding: 15px 0;
    overflow-y: auto;
}

.menu-section-title {
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    color: #475569;
    padding: 15px 24px 5px 24px;
    letter-spacing: 1px;
}

.menu-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 24px;
    color: #cbd5e1;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s ease;
    font-size: 0.95rem;
    font-weight: 500;
}

.menu-item:hover {
    background: rgba(255, 255, 255, 0.05);
    color: white;
}

.menu-item.active {
    background: linear-gradient(90deg, #1e293b, #1e40af);
    color: white;
    border-left: 4px solid #3b82f6;
}

.sidebar-score-box {
    background: #020617;
    margin: 15px;
    padding: 15px;
    border-radius: 12px;
    border: 1px dashed #334155;
}

.score-title {
    font-size: 0.75rem;
    font-weight: 700;
    color: #64748b;
    text-transform: uppercase;
    margin-bottom: 5px;
}

.score-value {
    font-size: 1.3rem;
    font-weight: 700;
    color: #10b981;
}

.sidebar-footer {
    padding: 15px;
    text-align: center;
    font-size: 0.75rem;
    color: #475569;
    border-top: 1px solid #1e293b;
}

/* ==========================================================================
   KONTAINER KONTEN UTAMA (KANAN)
   ========================================================================== */
.main-content {
    margin-left: 280px;
    flex: 1;
    padding: 40px;
    background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
    min-height: 100vh;
}

.content-header {
    margin-bottom: 30px;
    border-bottom: 2px solid #cbd5e1;
    padding-bottom: 15px;
}

.content-header h2 {
    color: #0f172a;
    font-size: 1.75rem;
    font-weight: 700;
}

.content-box {
    background: white;
    padding: 35px;
    border-radius: 16px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
    animation: fadeIn 0.4s ease-out;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

/* TOMBOL AKSI */
.btn-cool {
    display: inline-block;
    padding: 14px 35px;
    background: linear-gradient(45deg, #1e40af, #3b82f6);
    color: white;
    border: none;
    font-size: 1.05rem;
    font-weight: 600;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 8px 20px rgba(59, 130, 246, 0.3);
    transition: all 0.3s ease;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.btn-cool:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 24px rgba(59, 130, 246, 0.4);
    background: linear-gradient(45deg, #1d4ed8, #2563eb);
}

.btn-cool:active {
    transform: translateY(-1px);
}

.btn-logout {
    background: #ef4444;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
    font-size: 0.85rem;
    margin-top: 15px;
    transition: background 0.2s;
}

.btn-logout:hover {
    background: #dc2626;
}

/* Elemen Lembar Nilai Bundar */
.score-badge-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 30px 0;
}

.circle-score {
    width: 140px;
    height: 140px;
    border: 3px dashed #10b981;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.5rem;
    font-weight: 700;
    color: #047857;
    background: #ecfdf5;
    margin-bottom: 15px;
}

/* Blok Soal Pertanyaan */
.question-block {
    background: #f8fafc;
    padding: 20px;
    border-radius: 12px;
    margin-bottom: 15px;
    border-left: 5px solid #3b82f6;
    text-align: left;
}

input {
    width: 100%;
    padding: 12px 16px;
    border: 2px solid #cbd5e1;
    border-radius: 10px;
    font-size: 1rem;
    margin-top: 8px;
    box-sizing: border-box;
}

input:focus {
    border-color: #2563eb;
    outline: none;
}

select {
    width: 100%;
    padding: 10px;
    margin-top: 8px;
    border-radius: 8px;
    border: 1px solid #cbd5e1;
    background: white;
}

.hidden { display: none !important; }
</style>
</head>

<body>

<div id="leftSidebar" class="sidebar hidden">
    <div class="sidebar-brand">Sistem Pancasila</div>
    
    <div class="sidebar-menu">
        <div class="menu-section-title">Navigasi Utama</div>
        <div class="menu-item active" id="menu-beranda" onclick="bukaMenu('beranda')">
            <i data-lucide="home" style="width: 18px;"></i> Beranda Utama
        </div>
        
        <div class="menu-section-title">Pilihan Kuis Aktif</div>
        <div class="menu-item" id="menu-kuis1" onclick="bukaMenu('kuis1')">
            <i data-lucide="file-text" style="width: 18px;"></i> Kuis Pancasila 1
        </div>
        <div class="menu-item" id="menu-kuis2" onclick="bukaMenu('kuis2')">
            <i data-lucide="file-text" style="width: 18px;"></i> Kuis Pancasila 2
        </div>
        <div class="menu-item" id="menu-latihan1" onclick="bukaMenu('latihan1')">
            <i data-lucide="edit-3" style="width: 18px;"></i> Latihan Soal 1
        </div>
        <div class="menu-item" id="menu-latihan2" onclick="bukaMenu('latihan2')">
            <i data-lucide="edit-3" style="width: 18px;"></i> Latihan Soal 2
        </div>
        
        <div class="menu-section-title">Evaluasi</div>
        <div class="menu-item" id="menu-rekap" onclick="bukaMenu('rekap')">
            <i data-lucide="bar-chart-2" style="width: 18px;"></i> Rekap Nilai
        </div>
    </div>

    <div class="sidebar-score-box">
        <div class="score-title">Skor Sesi Terbaru:</div>
        <div class="score-value" id="sidebarSkor">Belum Ada</div>
    </div>

    <div class="sidebar-footer">
        &copy; 2026 Panel Evaluasi
    </div>
</div>


<div class="main-content" id="mainContentArea" style="margin-left: 0; width: 100%;">

    <div id="view-welcome" class="content-box" style="max-width: 600px; margin: 80px auto; text-align: center;">
        <h1 style="font-size: 2.2rem; margin-bottom: 12px; color: #0f172a;">🎓 SELAMAT DATANG DI KUIS</h1>
        <p style="color: #64748b; margin-bottom: 30px; font-size: 1.05rem;">Silakan masuk untuk mengakses sistem evaluasi Kuis & Latihan Pancasila.</p>
        <button class="btn-cool" onclick="pindahKeLoginBox()">Masuk Sistem</button>
    </div>

    <div id="view-login" class="content-box hidden" style="max-width: 450px; margin: 80px auto; text-align: center;">
        <h2>LOGIN MAHASISWA</h2>
        <p style="color: #64748b; margin-bottom: 25px; font-size: 0.9rem;">Gunakan kredensial akun akademik Anda</p>
        
        <div style="margin-bottom: 15px; text-align: left;">
            <input id="nim" placeholder="Masukkan NIM">
        </div>
        <div style="margin-bottom: 20px; text-align: left;">
            <input id="pass" type="password" placeholder="Masukkan Password">
        </div>
        
        <button class="btn-cool" style="width: 100%;" onclick="prosesLogin()">Masuk</button>
    </div>

    <div id="view-dashboard" class="hidden">
        
        <div class="content-header">
            <h2 id="pageTitle">Beranda Utama</h2>
        </div>

        <div id="sub-beranda" class="content-box">
            <h3 style="margin-bottom: 10px; color: #0f172a;">Selamat Datang di Pusat Evaluasi Mandiri!</h3>
            <p id="userDataInfo" style="margin-bottom: 20px; color: #475569; font-size: 1rem;"></p>
            <p style="line-height: 1.6; color: #64748b;">Gunakan panel menu navigasi di <b>sebelah kiri</b> layar laptop/komputer Anda untuk memilih Lembar Kuis atau melihat Rekap Nilai yang sudah dikerjakan.</p>
            <button class="btn-logout" onclick="prosesLogout()">Keluar Akun</button>
        </div>

        <div id="sub-ujian" class="content-box hidden">
            <div id="listSoalKuis"></div>
            <button class="btn-cool" style="background: linear-gradient(45deg, #10b981, #059669); width: 100%; margin-top: 25px; box-shadow: 0 6px 18px rgba(16, 185, 129, 0.3);" onclick="kalkulasiNilaiReal()">Simpan Semua Jawaban</button>
        </div>

        <div id="sub-rekap" class="content-box hidden" style="text-align: center;">
            <h3 style="color: #0f172a; margin-bottom: 5px;">Lembar Nilai Hasil Ujian</h3>
            <p style="color: #64748b; font-size: 0.9rem;">Nilai di bawah disinkronkan langsung secara realtime dengan indikator setbar kiri.</p>
            
            <div class="score-badge-container">
                <div class="circle-score" id="rekapMainScore">0/0</div>
            </div>

            <div style="max-width: 480px; margin: 0 auto; text-align: left; background: #f8fafc; padding: 25px; border-radius: 14px; border: 1px solid #e2e8f0;">
                <h4 style="margin-bottom: 15px; color: #1e293b; font-size: 0.95rem; text-transform: uppercase; letter-spacing: 0.5px;">Rincian Nilai Capaian:</h4>
                <p style="margin-bottom: 8px; font-size: 0.95rem;">Nilai Kuis 1 (200 Soal): <b id="rincianK1" style="color:#0f172a;">Belum Dikerjakan</b></p>
                <p style="margin-bottom: 8px; font-size: 0.95rem;">Nilai Kuis 2 (200 Soal): <b id="rincianK2" style="color:#0f172a;">Belum Dikerjakan</b></p>
                <p style="margin-bottom: 8px; font-size: 0.95rem;">Nilai Latihan 1: <b id="rincianL1" style="color:#0f172a;">Belum Dikerjakan</b></p>
                <p style="margin-bottom: 0px; font-size: 0.95rem;">Nilai Latihan 2: <b id="rincianL2" style="color:#0f172a;">Belum Dikerjakan</b></p>
            </div>
        </div>

    </div>

</div>

<script>
const VALID_USER = {
    nim: "45223099",
    pass: "123"
};

let kategoriAktif = "beranda";

// MASTER DATA DATABASE 200 SOAL DARI FILE KUIS MASTER PANCASILA ANDA
const DATABASE_SOAL_PANCASILA = [
    { no: 1, tanya: "Kapan BPUPKI dibentuk oleh pemerintah pendudukan Jepang?", a: "1 Maret 1945", b: "29 Mei 1945", c: "1 Juni 1945", d: "17 Agustus 1945", kunci: "A" },
    { no: 2, tanya: "Siapakah ketua dari BPUPKI (Badan Penyelidik Usaha-Usaha Persiapan Kemerdekaan Indonesia)?", a: "Ir. Soekarno", b: "Drs. Moh. Hatta", c: "Dr. K.R.T. Radjiman Wedyodiningrat", d: "Mr. Muhammad Yamin", kunci: "C" },
    { no: 3, tanya: "Kapan sidang pertama BPUPKI dilaksanakan?", a: "29 Mei - 1 Juni 1945", b: "10 Juli - 17 Juli 1945", c: "18 Agustus 1945", d: "22 Juni 1945", kunci: "A" },
    { no: 4, tanya: "Siapa sajakah tiga tokoh utama yang mengusulkan konsep dasar negara pada sidang pertama BPUPKI?", a: "Soekarno, Hatta, Subardjo", b: "Muhammad Yamin, Soepomo, Ir. Soekarno", c: "Radjiman, Agus Salim, Wahid Hasyim", d: "Ki Hadjar Dewantara, Sanusi, Tan Malaka", kunci: "B" },
    { no: 5, tanya: "Tokoh yang menyampaikan usulan dasar negara pada tanggal 29 Mei 1945 adalah...", a: "Mr. Soepomo", b: "Ir. Soekarno", c: "Drs. Moh. Hatta", d: "Mr. Muhammad Yamin", kunci: "D" },
    { no: 6, tanya: "Apa judul pidato yang disampaikan oleh Ir. Soekarno pada tanggal 1 Juni 1945?", a: "Indonesia Menggugat", b: "Larnya Pancasila", c: "Jalannya Revolusi Kita", d: "Manifesto Politik", kunci: "B" },
    { no: 193, tanya: "Realisasi nilai-nilai instrumental dalam bentuk tindakan nyata sehari-hari di masyarakat disebut sebagai...", a: "Nilai Dasar", b: "Nilai Praksis", c: "Nilai Material", d: "Nilai Rohani", kunci: "B" },
    { no: 194, tanya: "Pancasila sebagai ideologi terbuka harus mampu menyerap nilai baru yang positif tanpa menghilangkan...", a: "Nilai dasar dan identitas aslinya", b: "Pengaruh partai penguasa", c: "Struktur hukum kolonial", d: "Sistem pemerintahan parlementer", kunci: "A" },
    { no: 195, tanya: "Sikap menjunjung tinggi hak asasi manusia secara universal sangat selaras dengan nilai Pancasila Sila ke-...", a: "1 (Pertama)", b: "2 (Kedua)", c: "3 (Ketiga)", d: "4 (Keempat)", kunci: "B" },
    { no: 196, tanya: "Nilai Pancasila yang berbentuk pasal-pasal dalam UUD 1945 atau peraturan perundang-undangan organik dinamakan...", a: "Nilai Dasar", b: "Nilai Instrumental", c: "Nilai Praksis", d: "Nilai Vital", kunci: "B" },
    { no: 197, tanya: "Realisasi nilai-nilai instrumental dalam bentuk tindakan nyata sehari-hari di masyarakat disebut sebagai...", a: "Nilai Dasar", b: "Nilai Praksis", c: "Nilai Material", d: "Nilai Rohani", kunci: "B" },
    { no: 198, tanya: "Pancasila sebagai ideologi terbuka harus mampu menyerap nilai baru yang positif tanpa menghilangkan...", a: "Nilai dasar dan identitas aslinya", b: "Pengaruh partai penguasa", c: "Struktur hukum kolonial", d: "Sistem pemerintahan parlementer", kunci: "A" },
    { no: 199, tanya: "Sikap menjunjung tinggi hak asasi manusia secara universal sangat selaras dengan nilai Pancasila Sila ke-...", a: "1 (Pertama)", b: "2 (Kedua)", c: "3 (Ketiga)", d: "4 (Keempat)", kunci: "B" },
    { no: 200, tanya: "Nilai Pancasila yang berbentuk pasal-pasal dalam UUD 1945 dinamakan sebagai...", a: "Nilai Dasar", b: "Nilai Instrumental", c: "Nilai Praksis", d: "Nilai Vital", kunci: "B" }
];

lucide.createIcons();

function pindahKeLoginBox() {
    document.getElementById("view-welcome").classList.add("hidden");
    document.getElementById("view-login").classList.remove("hidden");
}

function prosesLogin() {
    let nimInput = document.getElementById("nim").value;
    let passInput = document.getElementById("pass").value;

    if (nimInput === VALID_USER.nim && passInput === VALID_USER.pass) {
        localStorage.setItem("session_login", "true");
        localStorage.setItem("session_nim", nimInput);
        muatTampilanAplikasi();
    } else {
        alert("NIM atau Password salah!");
    }
}

function prosesLogout() {
    localStorage.clear();
    location.reload();
}

function muatTampilanAplikasi() {
    document.getElementById("view-welcome").classList.add("hidden");
    document.getElementById("view-login").classList.add("hidden");
    
    document.getElementById("leftSidebar").classList.remove("hidden");
    document.getElementById("view-dashboard").classList.remove("hidden");
    
    let mainArea = document.getElementById("mainContentArea");
    mainArea.style.marginLeft = "280px";
    mainArea.style.width = "calc(100% - 280px)";

    let nimActive = localStorage.getItem("session_nim");
    document.getElementById("userDataInfo").innerHTML = "NIM Aktif: <b>" + nimActive + "</b> | Status: Terautentikasi";

    refreshIndikatorSkor();
    bukaMenu('beranda');
}

function bukaMenu(tipeMenu) {
    kategoriAktif = tipeMenu;

    document.querySelectorAll('.menu-item').forEach(el => el.classList.remove('active'));
    let targetMenu = document.getElementById("menu-" + tipeMenu);
    if (targetMenu) targetMenu.classList.add('active');

    document.getElementById("sub-beranda").classList.add("hidden");
    document.getElementById("sub-ujian").classList.add("hidden");
    document.getElementById("sub-rekap").classList.add("hidden");

    let headerTitle = document.getElementById("pageTitle");

    if (tipeMenu === 'beranda') {
        headerTitle.innerText = "Beranda Utama";
        document.getElementById("sub-beranda").classList.remove("hidden");
    } 
    else if (tipeMenu === 'rekap') {
        headerTitle.innerText = "Rekap Nilai";
        document.getElementById("sub-rekap").classList.remove("hidden");
        tampilkanHalamanRekapData();
    } 
    else {
        let limitSoal = 10;
        if(tipeMenu === 'kuis1') { headerTitle.innerText = "Kuis Pancasila 1 (200 Soal)"; limitSoal = 200; }
        if(tipeMenu === 'kuis2') { headerTitle.innerText = "Kuis Pancasila 2 (200 Soal)"; limitSoal = 200; }
        if(tipeMenu === 'latihan1') { headerTitle.innerText = "Latihan Soal 1"; limitSoal = 10; }
        if(tipeMenu === 'latihan2') { headerTitle.innerText = "Latihan Soal 2"; limitSoal = 10; }

        document.getElementById("sub-ujian").classList.remove("hidden");
        bangunDaftarPertanyaan(limitSoal);
    }
}

function bangunDaftarPertanyaan(jumlah) {
    let containerHtml = "";
    
    // Looping data soal asli dari master database
    let totalLoop = Math.min(jumlah, DATABASE_SOAL_PANCASILA.length);
    
    for (let i = 0; i < totalLoop; i++) {
        let dataSoal = DATABASE_SOAL_PANCASILA[i];
        containerHtml += `
        <div class="question-block">
            <p style="font-weight:600; margin-bottom:6px; color:#0f172a;">Pertanyaan Nomor ${i + 1}:</p>
            <p style="color:#475569; font-size:0.95rem; margin-bottom:10px;">${dataSoal.tanya}</p>
            <select id="opsiJawab${i}">
                <option value="">-- Pilih Jawaban --</option>
                <option value="A">A. ${dataSoal.a}</option>
                <option value="B">B. ${dataSoal.b}</option>
                <option value="C">C. ${dataSoal.c}</option>
                <option value="D">D. ${dataSoal.d}</option>
            </select>
        </div>`;
    }
    document.getElementById("listSoalKuis").innerHTML = containerHtml;
}

function kalkulasiNilaiReal() {
    let jumlahSoal = (kategoriAktif === 'kuis1' || kategoriAktif === 'kuis2') ? 200 : 10;
    let totalTersedia = Math.min(jumlahSoal, DATABASE_SOAL_PANCASILA.length);
    let jawabanBenar = 0;

    for (let i = 0; i < totalTersedia; i++) {
        let nilaiOpsi = document.getElementById("opsiJawab" + i).value;
        if (nilaiOpsi === DATABASE_SOAL_PANCASILA[i].kunci) {
            jawabanBenar++;
        }
    }

    let kalkulasiAkhir = Math.round((jawabanBenar / totalTersedia) * 100);
    localStorage.setItem("store_nilai_" + kategoriAktif, kalkulasiAkhir);
    localStorage.setItem("latest_score_view", kalkulasiAkhir);

    alert("Jawaban Berhasil Disimpan!\nNilai pengerjaan Anda: " + kalkulasiAkhir);
    
    refreshIndikatorSkor();
    bukaMenu('rekap');
}

function refreshIndikatorSkor() {
    let nilaiTerakhir = localStorage.getItem("latest_score_view");
    if (nilaiTerakhir !== null) {
        document.getElementById("sidebarSkor").innerText = nilaiTerakhir + " / 100";
    } else {
        document.getElementById("sidebarSkor").innerText = "Belum Ada";
    }
}

function tampilkanHalamanRekapData() {
    let k1 = localStorage.getItem("store_nilai_kuis1");
    let k2 = localStorage.getItem("store_nilai_kuis2");
    let l1 = localStorage.getItem("store_nilai_latihan1");
    let l2 = localStorage.getItem("store_nilai_latihan2");
    
    let skorTerbaru = localStorage.getItem("latest_score_view") || 0;

    document.getElementById("rekapMainScore").innerText = skorTerbaru + "/100";

    document.getElementById("rincianK1").innerText = k1 !== null ? k1 + " Poin" : "Belum Dikerjakan";
    document.getElementById("rincianK2").innerText = k2 !== null ? k2 + " Poin" : "Belum Dikerjakan";
    document.getElementById("rincianL1").innerText = l1 !== null ? l1 + " Poin" : "Belum Dikerjakan";
    document.getElementById("rincianL2").innerText = l2 !== null ? l2 + " Poin" : "Belum Dikerjakan";
}

if (localStorage.getItem("session_login") === "true") {
    muatTampilanAplikasi();
}
</script>

</body>
</html>
