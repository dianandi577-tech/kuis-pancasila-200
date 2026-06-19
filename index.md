<div class="dashboard-container">

  <!-- SIDEBAR (SEBELAH KIRI) -->
  <div class="sidebar">
    <h3>Kuis Pancasila</h3>
    <ul>
      <li><a href="#" class="active">🏠 Menu Utama</a></li>
      <li><a href="#">📊 Rekapitulasi Nilai</a></li>
      <li><a href="#">📝 Mulai Kuis</a></li>
      <li><a href="#">⚙️ Pengaturan</a></li>
    </ul>
  </div>

  <!-- KONTEN UTAMA (SEBELAH KANAN) -->
  <div class="main-content">
    
    <!-- MENU UTAMA SELAMAT DATANG -->
    <div class="welcome-section">
      <h1>👋 Selamat Datang di Aplikasi Kuis Pancasila</h1>
      <p>Silakan isi data diri Anda terlebih dahulu sebelum memulai kuis.</p>
      
      <!-- FORM INPUT NAMA & NIM -->
      <div class="profile-card">
        <h3>Data Peserta</h3>
        <div class="form-group">
          <label for="nama">Nama Lengkap:</label>
          <input type="text" id="nama" placeholder="Masukkan nama Anda...">
        </div>
        <div class="form-group">
          <label for="nim">NIM:</label>
          <input type="text" id="nim" placeholder="Masukkan NIM Anda...">
        </div>
        <button class="btn-save">Simpan Data</button>
      </div>
    </div>

    <!-- REKAPITULASI NILAI -->
    <div class="recap-section">
      <h2>📊 Rekapitulasi Nilai</h2>
      <div class="stats-container">
        <div class="stat-box shadow-sm">
          <h4>Kuis 1</h4>
          <p class="score">85</p>
        </div>
        <div class="stat-box shadow-sm">
          <h4>Kuis 2</h4>
          <p class="score">90</p>
        </div>
        <div class="stat-box shadow-sm">
          <h4>Rata-rata</h4>
          <p class="score total">87.5</p>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- CSS UNTUK MENGATUR TAMPILAN DASBOR -->
<style>
  .dashboard-container {
    display: flex;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: #333;
    margin: -16px;
    background-color: #f4f6f9;
    min-height: 100vh;
  }

  /* Gaya Sidebar Kiri */
  .sidebar {
    width: 250px;
    background-color: #2c3e50;
    color: white;
    padding: 20px;
    box-sizing: border-box;
  }
  .sidebar h3 {
    margin-top: 0;
    padding-bottom: 15px;
    border-bottom: 1px solid #34495e;
    text-align: center;
    color: #1abc9c;
  }
  .sidebar ul {
    list-style: none;
    padding: 0;
    margin: 20px 0;
  }
  .sidebar ul li {
    margin-bottom: 10px;
  }
  .sidebar ul li a {
    color: #ecf0f1;
    text-decoration: none;
    display: block;
    padding: 12px 15px;
    border-radius: 6px;
    transition: all 0.3s;
  }
  .sidebar ul li a:hover, .sidebar ul li a.active {
    background-color: #1abc9c;
    color: white;
  }

  /* Gaya Konten Utama */
  .main-content {
    flex: 1;
    padding: 30px;
    box-sizing: border-box;
  }
  .welcome-section {
    background-color: white;
    padding: 25px;
    border-radius: 8px;
    margin-bottom: 25px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  .welcome-section h1 {
    margin-top: 0;
    color: #2c3e50;
  }

  /* Form Nama & NIM */
  .profile-card {
    margin-top: 20px;
    padding: 20px;
    background-color: #f8f9fa;
    border-left: 5px solid #1abc9c;
    border-radius: 4px;
    max-width: 500px;
  }
  .profile-card h3 {
    margin-top: 0;
    margin-bottom: 15px;
  }
  .form-group {
    margin-bottom: 15px;
  }
  .form-group label {
    display: block;
    margin-bottom: 5px;
    font-weight: 600;
  }
  .form-group input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  .btn-save {
    background-color: #1abc9c;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
    transition: background 0.2s;
  }
  .btn-save:hover {
    background-color: #16a085;
  }

  /* Gaya Rekapitulasi Nilai */
  .recap-section {
    background-color: white;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }
  .recap-section h2 {
    margin-top: 0;
    color: #2c3e50;
    margin-bottom: 20px;
  }
  .stats-container {
    display: flex;
    gap: 20px;
  }
  .stat-box {
    flex: 1;
    background-color: #fff;
    border: 1px solid #e3e6f0;
    border-radius: 6px;
    padding: 20px;
    text-align: center;
  }
  .stat-box h4 {
    margin: 0 0 10px 0;
    color: #4e73df;
  }
  .stat-box .score {
    font-size: 28px;
    font-weight: bold;
    margin: 0;
    color: #5a5c69;
  }
  .stat-box .score.total {
    color: #e74c3c;
  }
  .shadow-sm {
    box-shadow: 0 .125rem .25rem 0 rgba(58,59,69,.05)!important;
  }
</style>
