<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Kuis Pancasila</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<style>
body {
    font-family: 'Poppins', Arial, sans-serif;
    margin: 0;
    /* Latar belakang gradasi estetik */
    background: linear-gradient(135deg, #0d3270 0%, #194b9b 40%, #e1b416 100%);
    background-size: cover;
    background-attachment: fixed;
    min-height: 100vh;
    padding: 20px;
    color: #333;
}

.box {
    width: 95%;
    max-width: 800px;
    margin: auto;
    margin-top: 30px;
    background: rgba(255, 255, 255, 0.95);
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.2);
    animation: fadeIn 0.5s ease-out;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}

h1, h2 {
    text-align: center;
    color: #0d3270;
    font-weight: 700;
    margin-bottom: 20px;
}

input {
    width: 100%;
    padding: 12px;
    margin-top: 12px;
    border: 2px solid #e2e8f0;
    border-radius: 10px;
    font-size: 1rem;
    box-sizing: border-box;
    transition: all 0.3s;
}

input:focus {
    border-color: #194b9b;
    outline: none;
    box-shadow: 0 0 8px rgba(25, 75, 155, 0.2);
}

/* 🌟 TOMBOL SELAMAT DATANG & LOGIN KEREN */
.btn-cool {
    display: block;
    width: 100%;
    max-width: 250px;
    margin: 25px auto 0 auto;
    padding: 14px 28px;
    background: linear-gradient(45deg, #194b9b, #2d6cdf);
    color: white;
    border: none;
    cursor: pointer;
    font-size: 1.1rem;
    font-weight: 600;
    border-radius: 50px;
    box-shadow: 0 8px 20px rgba(45, 108, 223, 0.4);
    transition: all 0.3s ease;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.btn-cool:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 26px rgba(45, 108, 223, 0.6);
    background: linear-gradient(45deg, #0d3270, #194b9b);
}

.btn-cool:active {
    transform: translateY(-1px);
}

/* Grid Menu Utama Dasbor */
.dashboard-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
    margin-top: 20px;
}

@media (max-width: 500px) {
    .dashboard-grid {
        grid-template-columns: 1fr;
    }
}

/* Tombol Menu Grid */
.menu-card {
    background: #f8fafc;
    border: 2px solid #e2e8f0;
    padding: 20px;
    border-radius: 14px;
    font-size: 1rem;
    font-weight: 600;
    color: #334155;
    cursor: pointer;
    transition: all 0.3s ease;
    text-align: center;
}

.menu-card:hover {
    border-color: #194b9b;
    background-color: #f0f4fa;
    transform: translateY(-3px);
    box-shadow: 0 6px 15px rgba(0,0,0,0.05);
}

.btn-logout {
    padding: 8px 16px;
    background: #ef4444;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    font-weight: 600;
    margin-top: 10px;
}

.btn-logout:hover {
    background: #dc2626;
}

.btn-submit {
    padding: 12px 24px;
    background: #10b981;
    color: white;
    border: none;
    border-radius: 10px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    margin-top: 15px;
    width: 100%;
}

.btn-submit:hover {
    background: #059669;
}

.hidden { display: none; }

.question {
    margin-top: 15px;
    padding: 15px;
    background: #f1f5f9;
    border-radius: 10px;
    border-left: 5px solid #194b9b;
    text-align: left;
}

select {
    width: 100%;
    padding: 8px;
    margin-top: 8px;
    border-radius: 6px;
    border: 1px solid #cbd5e1;
}
</style>
</head>

<body>

<!-- HALAMAN AWAL -->
<div id="welcome" class="box">
    <h1>🎓 SELAMAT DATANG DI KUIS</h1>
    <p style="text-align:center; color: #64748b;">Silakan masuk untuk mengakses Kuis & Latihan Pancasila</p>
    <!-- Tombol Keren Sesuai Permintaan -->
    <button class="btn-cool" onclick="showLogin()">Masuk Sistem</button>
</div>

<!-- LOGIN -->
<div id="loginBox" class="box hidden">
    <h2>LOGIN SISWA</h2>
    <input id="nim" placeholder="Masukkan NIM (Contoh: 45223099)">
    <input id="pass" type="password" placeholder="Masukkan Password (Contoh: 123)">
    <button class="btn-cool" onclick="login()">Login</button>
</div>

<!-- DASHBOARD UTAMA -->
<div id="dashboard" class="hidden">

    <!-- INFO PENGGUNA -->
    <div class="box" style="text-align: center;">
        <h2>👤 PANEL DASBOR</h2>
        <p id="userData" style="color: #475569; font-size: 1.05rem;"></p>
        <button class="btn-logout" onclick="logout()">Keluar Akun</button>
    </div>

    <!-- MENU UTAMA SESUAI PERMINTAAN -->
    <div class="box">
        <h3 style="text-align: center; color: #334155;">Silakan Pilih Menu Aktivitas:</h3>
        <div class="dashboard-grid">
            <div class="menu-card" onclick="bukaMenu('kuis1', '📘 KUIS PANCASILA 1 (200 Soal)')">📘 Kuis Pancasila 1</div>
            <div class="menu-card" onclick="bukaMenu('kuis2', '📕 KUIS PANCASILA 2 (200 Soal)')">📕 Kuis Pancasila 2</div>
            <div class="menu-card" onclick="bukaMenu('latihan1', '📝 LATIHAN SOAL 1')">📝 Latihan 1</div>
            <div class="menu-card" onclick="bukaMenu('latihan2', '✍️ LATIHAN SOAL 2')">✍️ Latihan 2</div>
            <div class="menu-card" style="grid-column: span 2; background: #e0f2fe; border-color: #bae6fd;" onclick="bukaMenu('rekap', '📊 REKAPITULASI NILAI')">📊 Rekap Nilai</div>
        </div>
    </div>

    <!-- WADAH DINAMIS UNTUK KUIS / LATIHAN -->
    <div id="kontenBox" class="box hidden">
        <h2 id="judulKonten">KUIS</h2>
        <div id="listSoal"></div>
        <button class="btn-submit" onclick="simpanNilai()">Simpan Semua Jawaban</button>
    </div>

    <!-- REKAP -->
    <div id="rekapBox" class="box hidden">
        <h2>REKAP NILAI</h2>
        <div style="background: #f8fafc; padding: 20px; border-radius: 12px; margin-top: 15px;">
            <p>Berikut adalah hasil pengerjaan sistem Anda:</p>
            <hr style="margin: 10px 0; border: 0; border-top: 1px solid #e2e8f0;">
            <p id="hasilKuis1">Nilai Kuis 1: <b>Belum Dikerjakan</b></p>
            <p id="hasilKuis2">Nilai Kuis 2: <b>Belum Dikerjakan</b></p>
            <p id="hasilLatihan1">Nilai Latihan 1: <b>Belum Dikerjakan</b></p>
            <p id="hasilLatihan2">Nilai Latihan 2: <b>Belum Dikerjakan</b></p>
        </div>
    </div>

</div>

<script>

// Akun login sesuai permintaan Anda
const USER = {
    nim: "45223099",
    pass: "123"
};

// Variabel menyimpan menu aktif saat ini
let menuAktif = "";

function showLogin(){
    document.getElementById("welcome").classList.add("hidden");
    document.getElementById("loginBox").classList.remove("hidden");
}

function login(){
    let nim = document.getElementById("nim").value;
    let pass = document.getElementById("pass").value;

    if(nim === USER.nim && pass === USER.pass){
        localStorage.setItem("login","true");
        localStorage.setItem("nim",nim);

        document.getElementById("loginBox").classList.add("hidden");
        document.getElementById("dashboard").classList.remove("hidden");

        document.getElementById("userData").innerHTML =
        "NIM Aktif: <b>"+nim+ "</b> | Status: Terautentikasi";
    }else{
        alert("NIM atau Password salah!");
    }
}

function logout(){
    localStorage.clear();
    location.reload();
}

function bukaMenu(type, judul) {
    // Sembunyikan semua kontainer konten terlebih dahulu
    document.getElementById("kontenBox").classList.add("hidden");
    document.getElementById("rekapBox").classList.add("hidden");
    
    menuAktif = type;

    if (type === 'rekap') {
        document.getElementById("rekapBox").classList.remove("hidden");
        tampilkanRekap();
    } else {
        document.getElementById("kontenBox").classList.remove("hidden");
        document.getElementById("judulKonten").innerText = judul;
        
        // Jika kuis 1 atau kuis 2, generate 200 soal. Jika latihan, buat 10 soal saja.
        let jumlahSoal = (type === 'kuis1' || type === 'kuis2') ? 200 : 10;
        generateSoal(jumlahSoal, judul);
    }
    
    // Geser layar ke bagian bawah menu agar langsung fokus ke soal
    document.getElementById("dashboard").scrollIntoView({ behavior: 'smooth', block: 'start' });
}

function generateSoal(jumlah, namaMenu){
    let html = "";
    for(let i=1; i<=jumlah; i++){
        html += `
        <div class="question">
            <p><b>Soal ${i}:</b> Ini adalah simulasi pertanyaan ke-${i} untuk ${namaMenu}.</p>
            <select id="jawab${i}">
                <option value="">-- Pilih Jawaban --</option>
                <option value="A">A. Pilihan Jawaban A</option>
                <option value="B">B. Pilihan Jawaban B</option>
                <option value="C">C. Pilihan Jawaban C</option>
                <option value="D">D. Pilihan Jawaban D</option>
            </select>
        </div>
        `;
    }
    document.getElementById("listSoal").innerHTML = html;
}

function simpanNilai(){
    let jumlahSoal = (menuAktif === 'kuis1' || menuAktif === 'kuis2') ? 200 : 10;
    let diisi = 0;

    for(let i=1; i<=jumlahSoal; i++){
        let j = document.getElementById("jawab"+i).value;
        if(j !== "") diisi++; 
    }

    // Hitung persentase nilai simulasi sederhana
    let nilai = Math.round((diisi / jumlahSoal) * 100);
    
    // Simpan nilai ke penyimpanan lokal browser berdasarkan menu yang dipilih
    localStorage.setItem("nilai_" + menuAktif, nilai);

    alert("Jawaban berhasil disimpan!\nNilai Anda untuk sesi ini: " + nilai);
    
    // Alihkan langsung ke halaman rekap setelah selesai menyimpan jawaban
    bukaMenu('rekap', '📊 REKAPITULASI NILAI');
}

function tampilkanRekap() {
    let k1 = localStorage.getItem("nilai_kuis1");
    let k2 = localStorage.getItem("nilai_kuis2");
    let l1 = localStorage.getItem("nilai_latihan1");
    let l2 = localStorage.getItem("nilai_latihan2");

    document.getElementById("hasilKuis1").innerHTML = "Nilai Kuis 1 (200 Soal): <b>" + (k1 !== null ? k1 : "Belum Dikerjakan") + "</b>";
    document.getElementById("hasilKuis2").innerHTML = "Nilai Kuis 2 (200 Soal): <b>" + (k2 !== null ? k2 : "Belum Dikerjakan") + "</b>";
    document.getElementById("hasilLatihan1").innerHTML = "Nilai Latihan 1: <b>" + (l1 !== null ? l1 : "Belum Dikerjakan") + "</b>";
    document.getElementById("hasilLatihan2").innerHTML = "Nilai Latihan 2: <b>" + (l2 !== null ? l2 : "Belum Dikerjakan") + "</b>";
}

// Cek Auto Login otomatis saat halaman di-refresh
if(localStorage.getItem("login") === "true"){
    document.getElementById("welcome").classList.add("hidden");
    document.getElementById("dashboard").classList.remove("hidden");
    let nim = localStorage.getItem("nim");
    document.getElementById("userData").innerHTML = "NIM Aktif: <b>"+nim+"</b> | Status: Terautentikasi (Sesi Aktif)";
}

</script>

</body>
</html>
