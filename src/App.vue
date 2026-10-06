<template>
  <div class="app-wrapper">
    <!-- NAVBAR -->
    <nav class="navbar navbar-expand-lg bg-white sticky-top shadow-sm py-3">
      <div class="container">
        <a class="navbar-brand fw-bold d-flex align-items-center" href="#" @click.prevent="currentView = 'landing'">
          <img src="/src/assets/logo versi warna.png" class="rounded me-2 d-flex justify-content-center align-items-center" style="width: 40px; height: 40px;" />
          <span class="text-dark fs-4">Sistem <span class="text-primary">Absensi</span></span>
        </a>
        <div class="d-flex align-items-center">
          <button v-if="currentView === 'dashboard'" class="btn btn-outline-danger btn-sm rounded-pill px-4 fw-bold" @click="logout">
            <i class="fas fa-sign-out-alt me-1"></i> Keluar
          </button>
          <button v-if="currentView === 'landing'" class="btn btn-primary rounded-pill px-4 py-2 fw-bold shadow-sm" @click="currentView = 'login'">
            Masuk Portal <i class="fas fa-arrow-right ms-2"></i>
          </button>
        </div>
      </div>
    </nav>

    <!-- 1. LANDING PAGE -->
    <div v-if="currentView === 'landing'" class="landing-page">
      <!-- (Konten Landing Page Tetap Sama Seperti Sebelumnya) -->
      <section class="hero-section bg-light-blue py-5">
        <div class="container py-5">
          <div class="row align-items-center">
            <div class="col-lg-6 mb-5 mb-lg-0 fade-in-up">
              <span class="badge bg-success-subtle text-success px-3 py-2 rounded-pill mb-3 fw-bold">Transformasi Digital Sekolah</span>
              <h1 class="fw-extrabold text-dark display-4 mb-4" style="line-height: 1.2;">
                Absensi Cerdas <br><span class="text-primary">& Validasi Akurat</span>
              </h1>
              <p class="lead text-secondary mb-5" style="font-size: 1.1rem;">
                Sistem presensi terpadu untuk guru menggunakan teknologi Face Recognition dan Geotagging lokasi. Mencegah manipulasi data secara real-time.
              </p>
              <button class="btn btn-primary btn-lg rounded-pill px-5 py-3 fw-bold shadow-lg" @click="currentView = 'login'">
                Mulai Akses Sistem
              </button>
            </div>
            <div class="col-lg-6 text-center position-relative fade-in-up" style="animation-delay: 0.2s;">
              <div class="hero-image-wrapper p-2 bg-white rounded-4 shadow-lg mx-auto position-relative" style="max-width: 500px;">
                 <img src="/foto guru.jpg" alt="Guru" class="img-fluid rounded-3" style="height: 350px; object-fit: cover; width: 100%;">
                 <div class="floating-card shadow-sm bg-white rounded-4 p-3 position-absolute d-flex align-items-center" style="bottom: -20px; left: -20px;">
                    <div class="bg-success rounded-circle p-2 text-white me-3"><i class="fas fa-check"></i></div>
                    <div><h6 class="mb-0 fw-bold">Wajah Terdeteksi</h6><small class="text-muted">Akurasi 99.8%</small></div>
                 </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Fitur Unggulan Section -->
      <section class="features-section py-5 bg-white">
        <div class="container py-5">
          <div class="text-center mb-5">
            <h2 class="fw-bold text-dark">Program & Fitur Unggulan</h2>
            <p class="text-muted">Teknologi modern untuk administrasi yang lebih baik</p>
          </div>
          <div class="row g-4">
            <div class="col-md-4 fade-in-up">
              <div class="card h-100 border-0 shadow-sm feature-card p-4 transition-hover">
                <div class="icon-box bg-primary-subtle text-primary rounded-3 mb-4 d-inline-flex justify-content-center align-items-center" style="width: 60px; height: 60px;">
                  <i class="fas fa-user-shield fs-3"></i>
                </div>
                <h5 class="fw-bold">Anti-Titip Absen</h5>
                <p class="text-muted mb-0">Validasi biometrik wajah memastikan hanya guru yang bersangkutan yang dapat melakukan presensi kehadiran.</p>
              </div>
            </div>
            <div class="col-md-4 fade-in-up" style="animation-delay: 0.1s;">
              <div class="card h-100 border-0 shadow-sm feature-card p-4 transition-hover">
                <div class="icon-box bg-success-subtle text-success rounded-3 mb-4 d-inline-flex justify-content-center align-items-center" style="width: 60px; height: 60px;">
                  <i class="fas fa-map-marker-alt fs-3"></i>
                </div>
                <h5 class="fw-bold">Geofencing GPS</h5>
                <p class="text-muted mb-0">Absensi dikunci berdasarkan radius koordinat sekolah. Memastikan kehadiran fisik di lingkungan kerja.</p>
              </div>
            </div>
            <div class="col-md-4 fade-in-up" style="animation-delay: 0.2s;">
              <div class="card h-100 border-0 shadow-sm feature-card p-4 transition-hover">
                <div class="icon-box bg-warning-subtle text-warning rounded-3 mb-4 d-inline-flex justify-content-center align-items-center" style="width: 60px; height: 60px;">
                  <i class="fas fa-bolt fs-3"></i>
                </div>
                <h5 class="fw-bold">Manajemen Real-time</h5>
                <p class="text-muted mb-0">Admin dapat memantau data kehadiran, keterlambatan, dan rekapitulasi harian secara instan.</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ================= SECTION PANDUAN PENGGUNAAN ================= -->
      <div class="container py-5 my-5">
        <div class="text-center mb-5">
          <h3 class="fw-bold text-dark">Cara Melakukan Presensi</h3>
          <p class="text-muted">Tiga langkah mudah untuk mencatat kehadiran Anda setiap hari.</p>
        </div>
        <div class="row text-center g-4">
          <!-- Langkah 1 -->
          <div class="col-md-4">
            <div class="p-4 shadow-sm rounded-4 bg-white h-100 border border-light transition-hover">
              <div class="bg-primary-subtle text-primary rounded-circle d-inline-flex align-items-center justify-content-center mb-3" style="width: 60px; height: 60px;">
                <i class="fas fa-sign-in-alt fs-4"></i>
              </div>
              <h5 class="fw-bold">1. Login Sistem</h5>
              <p class="text-muted small">Masuk menggunakan kredensial username yang telah didaftarkan oleh admin sekolah.</p>
            </div>
          </div>
          <!-- Langkah 2 -->
          <div class="col-md-4">
            <div class="p-4 shadow-sm rounded-4 bg-white h-100 border border-light transition-hover">
              <div class="bg-success-subtle text-success rounded-circle d-inline-flex align-items-center justify-content-center mb-3" style="width: 60px; height: 60px;">
                <i class="fas fa-camera fs-4"></i>
              </div>
              <h5 class="fw-bold">2. Scan Wajah</h5>
              <p class="text-muted small">Arahkan wajah ke kamera untuk verifikasi biometrik yang memastikan keaslian presensi Anda. Sistem akan melacak koordinat GPS secara otomatis untuk memastikan Anda berada di lingkungan SLB.</p>
            </div>
          </div>
          <!-- Langkah 3 -->
          <div class="col-md-4">
            <div class="p-4 shadow-sm rounded-4 bg-white h-100 border border-light transition-hover">
              <div class="bg-warning-subtle text-warning rounded-circle d-inline-flex align-items-center justify-content-center mb-3" style="width: 60px; height: 60px;">
                <i class="fas fa-map-marked-alt fs-4"></i>
              </div>
              <h5 class="fw-bold">3. Riwayat Kehadiran</h5>
              <p class="text-muted small">Sistem akan mencatat presensi hadir dan pulang Anda secara realtime.</p>
            </div>
          </div>
        </div>
      </div>

      <!-- ================= FOOTER SLB DHARMA ASIH ================= -->
      <footer class="bg-dark text-white py-5 mt-auto w-100">
        <div class="container">
          <div class="row g-4">
            
            <!-- Kolom 1: Brand & Deskripsi -->
            <div class="col-lg-6 col-md-12 mb-4 mb-lg-0">
              <h5 class="fw-bold mb-3 d-flex align-items-center">
                <img src="/logo.png" class="rounded me-2 d-flex justify-content-center align-items-center" style="width: 40px; height: 40px;" /> 
                SLB Dharma Asih Kraksaan
              </h5>
              <p class="text-white-50 small pe-lg-5">
                Sistem Informasi Presensi Cerdas berbasis pemindaian biometrik wajah dan geolokasi lokasi, dirancang khusus untuk meningkatkan kedisiplinan dan kemudahan administrasi tenaga pendidik.
              </p>
            </div>

            <!-- Kolom 2: Tautan -->
            <div class="col-lg-3 col-md-6 mb-4 mb-md-0">
              <h6 class="text-uppercase fw-bold mb-3 text-light">Menu Utama</h6>
              <ul class="list-unstyled mb-0 small">
                <li class="mb-2"><a href="#" @click.prevent="currentView = 'landing'" class="text-white-50 text-decoration-none custom-link">Beranda</a></li>
                <li class="mb-2"><a href="#" @click.prevent="currentView = 'login'" class="text-white-50 text-decoration-none custom-link">Masuk Portal</a></li>
              </ul>
            </div>

            <!-- Kolom 3: Kontak -->
            <div class="col-lg-3 col-md-6">
              <h6 class="text-uppercase fw-bold mb-3 text-light">Hubungi Kami</h6>
              <ul class="list-unstyled mb-0 small text-white-50">
                <li class="mb-2"><i class="fas fa-map-marker-alt me-2 text-success"></i> Jl. Mayjen Sutoyo No. 56, Patokan, Kecamatan Kraksaan, Kabupaten Probolinggo, Jawa Timur</li>
                <li class="mb-2"><i class="fas fa-envelope me-2 text-success"></i> sdlbbcdharmaasihkraksaan@gmail.com</li>
                <li><i class="fas fa-phone me-2 text-success"></i> (+62) 81234282371</li>
              </ul>
            </div>
          </div>
          
          <!-- Garis Pemisah -->
          <hr class="my-4 border-secondary">
          
          <!-- Copyright & Sosial Media -->
          <div class="d-flex justify-content-between align-items-center flex-wrap">
            <p class="mb-0 text-white-50 small">
              &copy; 2026 SLB Dharma Asih Kraksaan. Hak Cipta Dilindungi.
            </p>
            <div class="d-flex">
              <a href="https://www.facebook.com/pages/SLB%20Darma%20Asih%20Kraksaan/1403540146642218/" class="text-white-50 me-3 custom-link"><i class="fab fa-facebook-f"></i></a>
              <a href="https://www.instagram.com/slbdharmaasihkraksaan/" class="text-white-50 me-3 custom-link"><i class="fab fa-instagram"></i></a>
              <a href="https://www.youtube.com/@SLBDHARMAASIHKRAKSAAN" class="text-white-50 custom-link"><i class="fab fa-youtube"></i></a>
            </div>
          </div>
        </div>
      </footer>
    </div>

    <!-- 2. PORTAL LOGIN -->
    <div v-else-if="currentView === 'login'" class="login-page bg-light-blue d-flex align-items-center" style="min-height: calc(100vh - 80px);">
      <div class="container py-5">
        <div class="row justify-content-center fade-in-up">
          <div class="col-12 col-sm-10 col-md-8 col-lg-5">
            <div class="card border-0 shadow-lg rounded-4 overflow-hidden mx-auto" style="max-width: 400px; width: 100%; border-radius: 20px;">
              <div class="card-header bg-primary text-white text-center py-4 border-0">
                <h4 class="fw-bold mb-0">Login Sistem</h4>
                <p class="small mb-0 text-white-50">Silakan masuk dengan akun Anda</p>
              </div>
              <div class="card-body p-4 p-md-5 bg-white">
                <form @submit.prevent="handleLogin">
                  <div class="mb-4">
                    <label class="form-label fw-bold text-dark small">USERNAME</label>
                    <div class="input-group">
                      <span class="input-group-text bg-light border-end-0"><i class="fas fa-user text-muted"></i></span>
                      <input type="text" v-model="loginData.username" class="form-control bg-light border-start-0 ps-0 py-2" placeholder="Masukkan username" required>
                    </div>
                  </div>
                  <div class="mb-4">
                    <label class="form-label fw-bold text-dark small">PASSWORD</label>
                    <div class="input-group">
                      <span class="input-group-text bg-light border-end-0"><i class="fas fa-lock text-muted"></i></span>
                      <input type="password" v-model="loginData.password" class="form-control bg-light border-start-0 ps-0 py-2" placeholder="Masukkan password" required>
                    </div>
                  </div>
                  <button type="submit" class="btn btn-primary w-100 py-3 rounded-3 fw-bold shadow-sm" :disabled="isLoading">
                    {{ isLoading ? 'Memeriksa Kredensial...' : 'Masuk Sekarang' }}
                  </button>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- 3. DASHBOARD -->
    <div v-else-if="currentView === 'dashboard'" class="dashboard-page bg-light" style="min-height: calc(100vh - 80px);">
      <div class="container py-4 py-md-5 fade-in-up">
        
        <!-- Header Profil -->
        <div class="bg-white rounded-4 shadow-sm p-4 mb-4 d-flex justify-content-between align-items-center border-start border-5 border-primary">
          <div class="d-flex align-items-center">
            <div class="bg-primary-subtle text-primary rounded-circle d-flex justify-content-center align-items-center me-3" style="width: 50px; height: 50px;">
              <i class="fas fa-user-tie fs-4"></i>
            </div>
            <div>
              <h5 class="mb-0 fw-bold text-dark">{{ currentUser.nama }}</h5>
              <small class="text-muted">Login sebagai: <span class="badge bg-secondary text-uppercase">{{ currentUser.role }}</span></small>
            </div>
          </div>
          <div class="text-end d-none d-md-block">
            <p class="mb-0 fw-bold text-dark">{{ currentDate }}</p>
          </div>
        </div>

        <!-- ================= DASHBOARD ADMIN ================= -->
        <div v-if="currentUser.role === 'admin'" class="card border-0 shadow-sm rounded-4">
          <div class="card-header bg-white border-bottom-0 pt-4 pb-2 px-4">
            <ul class="nav nav-pills nav-fill gap-2 mobile-scroll-nav mb-4">
              <li class="nav-item">
                <a class="nav-link fw-bold rounded-pill" :class="{ 'active bg-primary': adminTab === 'users' }" href="#" @click.prevent="adminTab = 'users'">
                  <i class="fas fa-users-cog me-1"></i> Kelola User & Data
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link fw-bold rounded-pill text-dark" :class="{ 'active bg-primary text-white': adminTab === 'jadwal' }" href="#" @click.prevent="adminTab = 'jadwal'">
                  <i class="fas fa-calendar-alt me-1"></i> Jadwal Absensi
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link fw-bold rounded-pill text-dark" :class="{ 'active bg-primary text-white': adminTab === 'laporan' }" href="#" @click.prevent="adminTab = 'laporan'">
                  <i class="fas fa-chart-bar me-1"></i> Laporan & Export
                </a>
              </li>
            </ul>
          </div>
          
          <div class="card-body p-4 border-top">
            <!-- ADMIN TAB 1: Kelola User & Tambah Data -->
            <div v-if="adminTab === 'users'">
              <div class="row align-items-center mb-4">
                <div class="col-md-6 mb-3 mb-md-0">
                  <!-- Fitur Fuzzy Search -->
                  <div class="input-group shadow-sm rounded-pill overflow-hidden">
                    <span class="input-group-text bg-white border-0 ps-3"><i class="fas fa-search text-muted"></i></span>
                    <input type="text" v-model="searchQuery" class="form-control border-0 py-2" placeholder="Cari nama atau username...">
                  </div>
                </div>
                <div class="col-md-6 text-md-end">
                  <button class="btn btn-primary rounded-pill fw-bold px-4 shadow-sm" @click="bukaModalUser(null)">
                    <i class="fas fa-user-plus me-1"></i> Tambah Karyawan
                  </button>
                </div>
              </div>
              
              <div v-if="isProcessingPhoto" class="text-center py-5">
                <div class="spinner-grow text-primary mb-3" style="width: 3rem; height: 3rem;"></div>
                <h6 class="fw-bold text-dark">{{ statusMessage }}</h6>
              </div>

              <div class="table-responsive table-wrapper border p-2" v-show="!isProcessingPhoto">
                <table class="table table-hover align-middle mb-0">
                  <thead class="table-light text-muted small">
                    <tr>
                      <th class="py-3">NAMA LENGKAP</th>
                      <th class="py-3">USERNAME</th>
                      <th class="py-3">STATUS BIOMETRIK</th>
                      <th class="py-3 text-end">TINDAKAN (CRUD)</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for="guru in filteredGuru" :key="guru.id_user">
                      <td class="fw-bold text-dark py-3">{{ guru.nama }}</td>
                      <td class="text-muted py-3">@{{ guru.username }}</td>
                      <td class="py-3">
                        <span :class="['badge rounded-pill px-3 py-2', guru.status_wajah === 'Sudah' ? 'bg-success-subtle text-success' : 'bg-danger-subtle text-danger']">
                          <i :class="guru.status_wajah === 'Sudah' ? 'fas fa-check-circle me-1' : 'fas fa-times-circle me-1'"></i>
                          {{ guru.status_wajah }} Terdaftar
                        </span>
                      </td>
                      <td class="text-end py-3">
                        <!-- Upload Foto Langsung -->
                        <input type="file" accept="image/jpeg, image/png" class="d-none" :id="'upload-' + guru.id_user" @change="(e) => prosesUploadFoto(e, guru.id_user)">
                        <label :for="'upload-' + guru.id_user" class="btn btn-outline-primary btn-sm rounded-pill fw-bold px-3 cursor-pointer mb-0 me-1" title="Upload Wajah">
                          <i class="fas fa-camera"></i>
                        </label>
                        <!-- Edit & Delete -->
                        <button class="btn btn-outline-secondary btn-sm rounded-pill px-3 me-1" @click="bukaModalUser(guru)" title="Edit Profil">
                          <i class="fas fa-edit"></i>
                        </button>
                        <button class="btn btn-outline-danger btn-sm rounded-pill px-3" @click="hapusUser(guru.id_user)" title="Hapus Karyawan">
                          <i class="fas fa-trash"></i>
                        </button>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>

            <!-- ADMIN TAB 2: Kelola Jadwal -->
            <div v-if="adminTab === 'jadwal'">
               <h5 class="fw-bold mb-4 text-dark">Pengaturan Jadwal Kerja</h5>
               <div class="table-responsive table-wrapper border p-2">
                 <table class="table table-bordered align-middle">
                   <thead class="table-light">
                     <tr><th>Hari Kerja</th><th>Jam Masuk</th><th>Batas Keterlambatan</th><th>Jam Pulang</th><th>Aksi</th></tr>
                   </thead>
                   <tbody>
                     <tr v-for="jadwal in daftarJadwal" :key="jadwal.id">
                       <td class="fw-bold">{{ jadwal.hari }}</td>
                       <td>{{ jadwal.masuk }}</td>
                       <td>{{ jadwal.batas }}</td>
                       <td>{{ jadwal.pulang }}</td>
                       <td>
                         <button class="btn btn-sm btn-outline-primary rounded-pill px-3" @click="bukaModalJadwal(jadwal)">
                           <i class="fas fa-edit me-1"></i> Edit Jadwal
                         </button>
                       </td>
                     </tr>
                   </tbody>
                 </table>
               </div>
            </div>

            <!-- ADMIN TAB 3: Laporan & Export -->
            <div v-if="adminTab === 'laporan'">
              <div class="d-flex justify-content-between align-items-center mb-4">
                <h5 class="fw-bold mb-0 text-dark">Laporan Absensi</h5>
                <div>
                  <button class="btn btn-outline-danger btn-sm rounded-pill fw-bold px-3 me-2" @click="exportPDF">
                    <i class="fas fa-file-pdf me-1"></i> Export PDF
                  </button>
                  <button class="btn btn-success btn-sm rounded-pill fw-bold px-3 shadow-sm" @click="exportExcel">
                    <i class="fas fa-file-excel me-1"></i> Export Excel
                  </button>
                </div>
              </div>
              <div class="table-responsive table-wrapper border p-2">
                 <table class="table table-hover align-middle border">
                   <thead class="table-dark">
                     <tr><th>Tanggal</th><th>Nama Guru</th><th>Jam Masuk</th><th>Jam Pulang</th><th>Status Kehadiran</th><th>Lokasi</th><th class="text-end">Aksi</th></tr>
                   </thead>
                   <tbody>
                     <tr v-for="absen in laporanAbsensi" :key="absen.id">
                       <td>{{ absen.tanggal }}</td>
                       <td class="fw-bold">{{ absen.nama }}</td>
                       <td>{{ absen.jam_masuk }}</td>
                       <td>{{ absen.jam_keluar }}</td>
                       <td>
                         <span :class="['badge', absen.status === 'Hadir' ? 'bg-success' : (absen.status === 'Terlambat' ? 'bg-warning text-dark' : 'bg-danger')]">
                           {{ absen.status }}
                         </span>
                       </td>
                       <td class="text-muted" style="font-size: 0.9em; max-width: 200px; word-wrap: break-word;">
                          <!-- Jika sedang proses melacak alamat -->
                          <span v-if="absen.alamat === 'Melacak...'">
                            <i class="fas fa-spinner fa-spin me-1 text-primary"></i> Menerjemahkan GPS...
                          </span>
                          <!-- Jika alamat berhasil didapatkan -->
                          <span v-else-if="absen.alamat">
                            <i class="fas fa-map-marker-alt me-1 text-danger"></i> {{ absen.alamat }}
                          </span>
                          <!-- Jika gagal/tidak ada alamat, tampilkan angka asli -->
                          <span v-else-if="absen.latitude && absen.longitude">
                            <i class="fas fa-map-pin me-1"></i> {{ absen.latitude }}, {{ absen.longitude }}
                          </span>
                          <!-- Jika absen tanpa GPS -->
                          <span v-else class="text-danger fst-italic">Tidak terdata</span>
                        </td>
                       <td class="text-end">
                         <button class="btn btn-sm btn-outline-secondary rounded-pill" @click="bukaModalLaporan(absen)">
                           <i class="fas fa-edit"></i> Edit
                         </button>
                         <button class="btn btn-sm btn-outline-danger" @click="hapusLaporan(absen.id)">
                            <i class="fas fa-trash-alt"></i> Hapus
                         </button>
                       </td>
                     </tr>
                     <tr v-if="laporanAbsensi.length === 0">
                        <td colspan="7" class="text-center text-muted py-4">Belum ada data laporan absensi.</td>
                      </tr>
                   </tbody>
                 </table>
               </div>
            </div>
          </div>
        </div>

        <!-- ================= DASHBOARD USER ================= -->
        <!-- (Konten Dashboard User Tetap Sama Seperti Sebelumnya) -->
        <div v-if="currentUser.role === 'user'" class="card border-0 shadow-sm rounded-4 overflow-hidden">
          <div class="card-header bg-white border-bottom-0 pt-4 pb-2 px-4">
            <ul class="nav nav-pills nav-fill gap-2 mobile-scroll-nav mb-4">
              <li class="nav-item">
                <a class="nav-link fw-bold rounded-pill" :class="{ 'active bg-primary': userTab === 'absen' }" href="#" @click.prevent="userTab = 'absen'">
                  <i class="fas fa-camera me-1"></i> Absen Wajah
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link fw-bold rounded-pill text-dark" :class="{ 'active bg-primary text-white': userTab === 'riwayat' }" href="#" @click.prevent="userTab = 'riwayat'">
                  <i class="fas fa-history me-1"></i> Riwayat Absensi
                </a>
              </li>
            </ul>
          </div>
          <div class="card-body p-0 border-top">
            <div v-if="userTab === 'absen'" class="p-4 p-md-5 bg-light-blue text-center">
              <h5 class="fw-bold text-dark mb-4">Pindai Wajah & Lokasi</h5>
              <div :class="['alert py-3 fw-bold rounded-3 mb-4 shadow-sm border-0 text-start d-flex align-items-center', statusColor]">
                <i :class="['fs-4 me-3', statusIcon]"></i>{{ statusMessage }}
              </div>
              <div class="camera-container ratio ratio-4x3 bg-dark rounded-4 overflow-hidden shadow-lg mx-auto position-relative border border-4 border-white mb-4" style="max-width: 500px;">
                <video ref="videoElUser" autoplay muted playsinline class="camera-video w-100 h-100 object-fit-cover"></video>
                <div class="scan-line" v-if="isLoading"></div>
              </div>
              <div class="row g-2 mx-auto" style="max-width: 500px;">
                <div class="col-6">
                  <button class="btn btn-sm btn-primary btn-lg w-100 py-3 rounded-pill fw-bold shadow-sm" @click="prosesAbsensiUser('masuk')" :disabled="isLoading || !isCameraReady">
                    <span v-if="isLoading" class="spinner-border spinner-border-sm"></span>
                    <span v-else><i class="fas fa-sign-in-alt me-1"></i> Hadir</span>
                  </button>
                </div>
                <div class="col-6">
                  <button class="btn btn-outline-danger bg-red btn-white w-100 py-3 rounded-pill fw-bold shadow-sm" @click="prosesAbsensiUser('keluar')" :disabled="isLoading || !isCameraReady">
                    <span v-if="isLoading" class="spinner-border spinner-border-sm"></span>
                    <span v-else><i class="fas fa-sign-out-alt me-1"></i> Pulang</span>
                  </button>
                </div>
              </div>
            </div>
            <div v-if="userTab === 'riwayat'" class="p-4">
              <h5 class="fw-bold mb-4 text-dark">Riwayat Kehadiran Anda</h5>
              <div class="table-responsive table-wrapper border p-2">
                 <table class="table table-hover align-middle border">
                   <thead class="table-light">
                     <tr>
                       <th>Tanggal</th>
                       <th>Jam Masuk</th>
                       <th>Jam Pulang</th>
                       <th>Status</th>
                       <th class="text-center">Lokasi Map</th>
                     </tr>
                   </thead>
                   <tbody>
                     <tr v-for="riwayat in riwayatUser" :key="riwayat.id">
                       <td>{{ riwayat.tanggal }}</td>
                       <td class="fw-bold">{{ riwayat.jam_masuk || '-' }}</td>
                       <td>{{ riwayat.jam_keluar || '-' }}</td>
                       <td>
                         <span :class="['badge', riwayat.status === 'Hadir' ? 'bg-success' : (riwayat.status === 'Terlambat' ? 'bg-warning text-dark' : 'bg-danger')]">
                           {{ riwayat.status }}
                         </span>
                       </td>
                       <td class="text-center">
                         <!-- Tombol Lihat di Google Maps -->
                         <a v-if="riwayat.latitude && riwayat.longitude" 
                            :href="'https://www.google.com/maps/search/?api=1&query=' + riwayat.latitude + ',' + riwayat.longitude" 
                            target="_blank" 
                            class="btn btn-sm btn-outline-primary rounded-pill px-3 fw-bold">
                           <i class="fas fa-map-marker-alt me-1"></i> Buka Map
                         </a>
                         <span v-else class="badge bg-secondary rounded-pill">Lokasi Tidak Terdata</span>
                       </td>
                     </tr>
                     <tr v-if="riwayatUser.length === 0">
                       <td colspan="5" class="text-center text-muted py-4">Belum ada riwayat kehadiran.</td>
                     </tr>
                   </tbody>
                 </table>
               </div>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- ================= MODAL OVERLAYS ================= -->
    <!-- Modal Tambah/Edit Karyawan -->
    <div v-if="showModalUser" class="modal fade show custom-modal-overlay" tabindex="-1">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content border-0 shadow-lg rounded-4">
          <div class="modal-header bg-primary text-white border-0 rounded-top-4">
            <h5 class="modal-title fw-bold">{{ formUser.id_user ? 'Edit Karyawan' : 'Tambah Karyawan Baru' }}</h5>
            <button type="button" class="btn-close btn-close-white" @click="showModalUser = false"></button>
          </div>
          <div class="modal-body p-4">
            <div class="mb-3">
              <label class="form-label fw-bold small">Nama Lengkap</label>
              <input type="text" v-model="formUser.nama" class="form-control bg-light" placeholder="Masukkan nama lengkap" required>
            </div>
            <div class="mb-3">
              <label class="form-label fw-bold small">Username</label>
              <input type="text" v-model="formUser.username" class="form-control bg-light" placeholder="Masukkan username" required>
            </div>
            <div class="mb-3">
              <label class="form-label fw-bold small">Password</label>
              <input type="password" v-model="formUser.password" class="form-control bg-light" :placeholder="formUser.id_user ? 'Kosongkan jika tidak ingin ganti' : 'Masukkan password'" required>
            </div>
            <div class="mb-4" v-if="!formUser.id_user">
              <label class="form-label fw-bold small">Upload Sampel Foto (Wajah Depan)</label>
              <input type="file" class="form-control bg-light" accept="image/jpeg, image/png" @change="handleFileBaru">
              <small class="text-muted">Foto digunakan untuk registrasi awal Face Recognition.</small>
            </div>
          </div>
          <div class="modal-footer border-0 bg-light rounded-bottom-4">
            <button class="btn btn-secondary rounded-pill px-4" @click="showModalUser = false">Batal</button>
            <button class="btn btn-primary rounded-pill px-4 fw-bold" @click="simpanUser">Simpan Data</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal Edit Jadwal -->
    <div v-if="showModalJadwal" class="modal fade show custom-modal-overlay" tabindex="-1">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content border-0 shadow-lg rounded-4">
          <div class="modal-header bg-primary text-white border-0 rounded-top-4">
            <h5 class="modal-title fw-bold">Edit Jadwal: {{ formJadwal.hari }}</h5>
            <button type="button" class="btn-close btn-close-white" @click="showModalJadwal = false"></button>
          </div>
          <div class="modal-body p-4">
            <div class="mb-3">
              <label class="form-label fw-bold small">Hari Kerja</label>
              <input type="text" v-model="formJadwal.hari" class="form-control bg-light">
            </div>
            <div class="mb-3">
              <label class="form-label fw-bold small">Jam Masuk</label>
              <input type="time" v-model="formJadwal.masuk" class="form-control bg-light">
            </div>
            <div class="mb-3">
              <label class="form-label fw-bold small">Batas Keterlambatan</label>
              <input type="time" v-model="formJadwal.batas" class="form-control bg-light">
            </div>
            <div class="mb-4">
              <label class="form-label fw-bold small">Jam Pulang</label>
              <input type="time" v-model="formJadwal.pulang" class="form-control bg-light">
            </div>
          </div>
          <div class="modal-footer border-0 bg-light rounded-bottom-4">
            <button class="btn btn-secondary rounded-pill px-4" @click="showModalJadwal = false">Batal</button>
            <button class="btn btn-primary rounded-pill px-4 fw-bold" @click="simpanJadwal">Simpan Jadwal</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal Edit Laporan -->
    <div v-if="showModalLaporan" class="modal fade show custom-modal-overlay" tabindex="-1">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content border-0 shadow-lg rounded-4">
          <div class="modal-header bg-primary text-white border-0 rounded-top-4">
            <h5 class="modal-title fw-bold">Edit Kehadiran: {{ formLaporan.nama }}</h5>
            <button type="button" class="btn-close btn-close-white" @click="showModalLaporan = false"></button>
          </div>
          <div class="modal-body p-4">
            <div class="mb-3">
              <label class="form-label fw-bold small">Jam Masuk</label>
              <input type="time" v-model="formLaporan.jam_masuk" class="form-control bg-light">
            </div>
            <div class="mb-4">
              <label class="form-label fw-bold small">Status Kehadiran</label>
              <select v-model="formLaporan.status" class="form-select bg-light">
                <option value="Hadir">Hadir</option>
                <option value="Terlambat">Terlambat</option>
                <option value="Izin">Izin</option>
                <option value="Alfa">Alfa</option>
              </select>
            </div>
          </div>
          <div class="modal-footer border-0 bg-light rounded-bottom-4">
            <button class="btn btn-secondary rounded-pill px-4" @click="showModalLaporan = false">Batal</button>
            <button class="btn btn-primary rounded-pill px-4 fw-bold" @click="simpanLaporan">Update Laporan</button>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>
import { ref, watch, nextTick, onMounted, computed } from 'vue';
import axios from 'axios';
import * as faceapi from 'face-api.js';
import Fuse from 'fuse.js';
import { jsPDF } from 'jspdf';
import autoTable from 'jspdf-autotable';
import * as XLSX from 'xlsx';
import Swal from 'sweetalert2';

const apiBase = 'https://absensi-backend-production-7eda.up.railway.app/api'; 

// State Global & UI
const currentView = ref('landing');
const adminTab = ref('users');
const userTab = ref('absen');
const isLoading = ref(false);
const isProcessingPhoto = ref(false);
const isCameraReady = ref(false);
const statusMessage = ref('Sistem siap digunakan.');
const statusColor = ref('bg-primary-subtle text-primary-emphasis');
const statusIcon = ref('fas fa-info-circle');
const currentUser = ref({});
const loginData = ref({ username: '', password: '' });
const videoElUser = ref(null);

const currentDate = computed(() => {
  return new Date().toLocaleDateString('id-ID', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
});

// State Data
const listGuru = ref([]);
const searchQuery = ref('');
const daftarJadwal = ref('');
const laporanAbsensi = ref([]);
const riwayatUser = ref([]);

const filteredGuru = computed(() => {
  if (!searchQuery.value) return listGuru.value;
  const fuse = new Fuse(listGuru.value, { keys: ['nama', 'username'], threshold: 0.3 });
  return fuse.search(searchQuery.value).map(result => result.item);
});

// State Modals
const showModalUser = ref(false);
const showModalJadwal = ref(false);
const showModalLaporan = ref(false);
const formUser = ref({ id_user: null, nama: '', username: '', password: '', fileFoto: null });
const formJadwal = ref({ id: null, hari: '', masuk: '', batas: '', pulang: '' });
const formLaporan = ref({ id: null, nama: '', jam_masuk: '', status: '' });

// ================= SISTEM SESSION & LOAD AI =================
const isModelLoaded = ref(false);
const muatModelAI = async () => {
  if (isModelLoaded.value) return true;
  try {
    statusMessage.value = 'Memuat AI Model dari Server Resmi...';
    const MODEL_URL = 'https://justadudewhohacks.github.io/face-api.js/models';
    await faceapi.nets.tinyFaceDetector.loadFromUri(MODEL_URL);
    await faceapi.nets.faceLandmark68Net.loadFromUri(MODEL_URL);
    await faceapi.nets.faceRecognitionNet.loadFromUri(MODEL_URL);
    isModelLoaded.value = true;
    statusMessage.value = 'AI Siap digunakan.';
    return true;
  } catch (err) {
    statusMessage.value = 'Error AI Model. Pastikan koneksi internet stabil.';
    return false;
  }
};

watch(currentView, (newView) => {
  localStorage.setItem('currentView', newView);
});

onMounted(async () => {
  const savedUser = localStorage.getItem('currentUser');
  const savedView = localStorage.getItem('currentView');

  if (savedUser) {
    // 1. JIKA SUDAH LOGIN: Arahkan otomatis ke dashboard
    currentUser.value = JSON.parse(savedUser);
    currentView.value = 'dashboard';
    
    // Panggil data dari database sesuai role
    if (currentUser.value.role === 'admin') {
      if (typeof fetchUsers === 'function') fetchUsers();
      if (typeof fetchJadwal === 'function') fetchJadwal();
    }
  } else {
    // 2. JIKA BELUM LOGIN: Izinkan hanya di halaman 'landing' atau 'login'
    if (savedView === 'login') {
      currentView.value = 'login';
    } else {
      currentView.value = 'landing';
      localStorage.setItem('currentView', 'landing');
    }
  }

  // Load Model AI secara asinkron di latar belakang
  await muatModelAI();
});

const handleLogin = async () => {
    isLoading.value = true;

    try {
        const res = await axios.post(`${apiBase}/login`, loginData.value);

        // Backend mengirim { message, user }
        const user = res.data.user;

        console.log('DATA LOGIN:', res.data);
        console.log('USER:', user);

        if (!user || !user.role) {
            throw new Error('Data user tidak ditemukan dari server.');
        }

        currentUser.value = user;

        localStorage.setItem(
            'currentUser',
            JSON.stringify(user)
        );

        currentView.value = 'dashboard';

        // Jalankan data sesuai role
        if (user.role === 'admin') {
            await fetchUsers();
            await fetchJadwal();
        }

        if (user.role === 'user') {
            await fetchRiwayatUser();
        }

    } catch (err) {
        console.error('LOGIN ERROR:', err);

        alert(
            err.response?.data?.error ||
            err.message ||
            'Username atau password salah!'
        );
    } finally {
        isLoading.value = false;
    }
};

const logout = () => {
  if (typeof stopKamera === 'function') stopKamera();
  currentUser.value = {};
  loginData.value = { username: '', password: '' };
  localStorage.removeItem('currentUser');
  localStorage.removeItem('currentView');
  currentView.value = 'landing';
};

// ================= FUNGSI FETCH DATA =================
const fetchUsers = async () => {
  try {
    const res = await axios.get(`${apiBase}/users`);
    listGuru.value = res.data;
  } catch (err) { console.error(err); }
};
const fetchLaporan = async () => {
  try {
    const res = await axios.get(`${apiBase}/laporan`);
    laporanAbsensi.value = res.data;

    // Loop untuk mengecek apakah ada baris yang alamatnya masih kosong (NULL)
    for (let i = 0; i < laporanAbsensi.value.length; i++) {
      let item = laporanAbsensi.value[i];

      // Jika kolom alamat dari database kosong TAPI ada data koordinatnya
      if (!item.alamat && item.latitude && item.longitude) {
        
        item.alamat = 'Mencari nama tempat...'; 
        
        // Jeda 1.5 detik per baris untuk menghindari pemblokiran server peta (OpenStreetMap)
        setTimeout(async () => {
          try {
            const url = `https://nominatim.openstreetmap.org/reverse?format=jsonv2&lat=${item.latitude}&lon=${item.longitude}&zoom=18`;
            const mapRes = await axios.get(url, { headers: { 'Accept-Language': 'id-ID' } });
            
            let alamatFinal = `${item.latitude}, ${item.longitude}`; // Default jika gagal menyusun teks

            if (mapRes.data && mapRes.data.address) {
              const a = mapRes.data.address;
              const namaTempat = a.amenity || a.building || a.office || a.road || '';
              const desa = a.village || a.suburb || a.neighbourhood || '';
              const kec = a.city_district || a.county || '';
              const kota = a.city || a.town || '';
              
              const arr = [];
              if (namaTempat) arr.push(namaTempat);
              if (desa && !arr.includes(desa)) arr.push(desa);
              if (kec && !arr.includes(kec)) arr.push(kec);
              if (kota && !arr.includes(kota)) arr.push(kota);
              
              if(arr.length > 0) {
                 alamatFinal = arr.join(', ');
              }
            }
            
            // 1. Tampilkan hasilnya langsung di tabel web (Vue)
            item.alamat = alamatFinal;

            // 2. SIMPAN HASILNYA KE DATABASE MYSQL SECARA PERMANEN
            await axios.put(`${apiBase}/laporan/update-alamat/${item.id}`, {
              alamat: alamatFinal
            });

          } catch (err) {
            item.alamat = `${item.latitude}, ${item.longitude}`;
          }
        }, i * 1500); 
      }
    }
  } catch (err) {
    console.error("Gagal mengambil laporan absensi:", err);
  }
};
const fetchRiwayatUser = async () => {
  try {
    const res = await axios.get(`${apiBase}/riwayat/${currentUser.value.id_user}`);
    riwayatUser.value = res.data;
  } catch (err) { console.error(err); }
};
const fetchJadwal = async () => {
  try {
    const res = await axios.get(`${apiBase}/jadwal`);
    if (res.data) {
      // Potong format detik (:00) agar rapi di input jam HTML
      daftarJadwal.value = [{
        id: res.data.id,
        hari: res.data.hari,
        masuk: res.data.masuk.slice(0, 5),
        batas: res.data.batas.slice(0, 5),
        pulang: res.data.pulang.slice(0, 5)
      }];
    }
  } catch (err) { console.error("Gagal mengambil jadwal:", err); }
};

// ================= FUNGSI JADWAL =================

const bukaModalJadwal = (jadwal) => {
  // Salin data dari tabel ke dalam form modal
  formJadwal.value = { 
    id: jadwal.id, 
    hari: jadwal.hari, 
    masuk: jadwal.masuk, 
    batas: jadwal.batas, 
    pulang: jadwal.pulang 
  };
  // Tampilkan modal
  showModalJadwal.value = true;
};

const simpanJadwal = async () => {
  try {
    await axios.put(`${apiBase}/jadwal/${formJadwal.value.id}`, {
      hari: formJadwal.value.hari,
      masuk: formJadwal.value.masuk,
      batas: formJadwal.value.batas,
      pulang: formJadwal.value.pulang
    });
    Swal.fire({
      icon: 'success',
      title: 'Berhasil!',
      text: 'Jadwal kerja berhasil diperbarui.',
      timer: 2000,
      showConfirmButton: false
    });
    showModalJadwal.value = false;
    fetchJadwal();
  } catch (err) {
    Swal.fire('Gagal!', 'Terjadi kesalahan saat memperbarui jadwal.', 'error');
  }
};

// ================= FUNGSI NOTIFIKASI MODERN (SWEETALERT2) =================
const showToast = (icon, title) => {
  Swal.fire({
    toast: true,
    position: 'top-end',
    icon: icon,
    title: title,
    showConfirmButton: false,
    timer: 3000,
    timerProgressBar: true
  });
};

// ================= FUNGSI CRUD & UPLOAD ADMIN =================
const bukaModalUser = (guru) => {
  formUser.value = guru ? { ...guru, password: '', fileFoto: null } : { id_user: null, nama: '', username: '', password: '', fileFoto: null };
  showModalUser.value = true;
};
const handleFileBaru = (event) => formUser.value.fileFoto = event.target.files[0];

const simpanUser = async () => {
  try {
    if (formUser.value.id_user) {
      await axios.put(`${apiBase}/users/${formUser.value.id_user}`, {
        nama: formUser.value.nama, username: formUser.value.username, password: formUser.value.password 
      });
      showToast('success', 'Data karyawan berhasil diperbarui!');
    } else {
      const res = await axios.post(`${apiBase}/users`, {
        nama: formUser.value.nama, username: formUser.value.username, password: formUser.value.password, role: 'user'
      });
      if (formUser.value.fileFoto) {
        await prosesEkstrakDanUpload(formUser.value.fileFoto, res.data.id_user);
      } else {
        showToast('success', 'Karyawan ditambahkan (Tanpa sampel foto).');
      }
    }
    showModalUser.value = false;
    fetchUsers();
  } catch (err) {
    Swal.fire('Gagal!', err.response?.data?.error || err.message, 'error');
  }
};

const hapusUser = async (id) => {
  const result = await Swal.fire({
    title: 'Hapus Karyawan?',
    text: 'Data karyawan beserta sampel biometrik wajahnya akan dihapus permanen dari sistem.',
    icon: 'warning',
    showCancelButton: true,
    confirmButtonColor: '#d33',
    cancelButtonColor: '#6c757d',
    confirmButtonText: 'Ya, Hapus!',
    cancelButtonText: 'Batal'
  });

  if (result.isConfirmed) {
    try {
      await axios.delete(`${apiBase}/users/${id}`);
      showToast('success', 'Karyawan berhasil dihapus.');
      fetchUsers();
    } catch (err) {
      Swal.fire('Error!', 'Gagal menghapus data dari database.', 'error');
    }
  }
};

const prosesUploadFoto = async (event, id_user) => {
  const file = event.target.files[0];
  if (!file) return;
  await prosesEkstrakDanUpload(file, id_user);
  event.target.value = ''; 
};

const prosesEkstrakDanUpload = async (file, id_user) => {
  if (!isModelLoaded.value) await muatModelAI();
  isProcessingPhoto.value = true;
  
  return new Promise((resolve) => {
    const reader = new FileReader();
    reader.readAsDataURL(file);
    reader.onload = (e) => {
      const img = new Image();
      img.src = e.target.result;
      img.onload = async () => {
        try {
          const canvas = document.createElement('canvas');
          canvas.width = img.width;
          canvas.height = img.height;
          canvas.getContext('2d').drawImage(img, 0, 0);

          const detections = await faceapi.detectSingleFace(canvas, new faceapi.TinyFaceDetectorOptions()).withFaceLandmarks().withFaceDescriptor();
          if (!detections) {
            Swal.fire('Wajah Tidak Terdeteksi', 'Pastikan foto menghadap depan, terang, dan tidak buram.', 'warning');
            isProcessingPhoto.value = false;
            return resolve(false);
          }

          const fotoBase64 = canvas.toDataURL('image/jpeg', 0.8);
          await axios.post(`${apiBase}/register-face`, {
            id_user: id_user, face_descriptor: Array.from(detections.descriptor), foto_base64: fotoBase64
          });
          showToast('success', 'Biometrik wajah berhasil didaftarkan!');
          fetchUsers();
          isProcessingPhoto.value = false;
          resolve(true);
        } catch (err) {
          Swal.fire('Error AI', err.message, 'error');
          isProcessingPhoto.value = false;
          resolve(false);
        }
      };
    };
  });
};

// ================= FUNGSI ABSENSI USER (KAMERA & GPS) =================
const startKameraUser = async () => {
  if (!videoElUser.value) return;
  statusMessage.value = 'Menghubungkan kamera...';
  try {
    const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: 'user' } });
    videoElUser.value.srcObject = stream;
    videoElUser.value.onloadedmetadata = () => {
      statusMessage.value = 'Kamera aktif. Posisikan wajah Anda.';
      isCameraReady.value = true;
    };
  } catch (err) {
    statusMessage.value = 'Kamera ditolak.';
    isCameraReady.value = false;
  }
};
const stopKamera = () => {
  if (videoElUser.value && videoElUser.value.srcObject) {
    videoElUser.value.srcObject.getTracks().forEach(track => track.stop());
    isCameraReady.value = false;
  }
};

const dapatkanGPS = () => {
  return new Promise((resolve, reject) => {
    if (!navigator.geolocation) return reject('GPS tidak didukung.');
    navigator.geolocation.getCurrentPosition(
      (pos) => resolve({ latitude: pos.coords.latitude, longitude: pos.coords.longitude }),
      (err) => reject('Akses Lokasi (GPS) ditolak/Timeout!'),
      { enableHighAccuracy: true, timeout: 5000, maximumAge: 0 }
    );
  });
};

const KOORDINAT_SEKOLAH = {
  latitude: -7.759335,   // Lat SLB Dharma Asih Kraksaan
  longitude: 113.4138725  // Long SLB Dharma Asih Kraksaan
};

const BATAS_RADIUS_METER = 150; // Jarak toleransi absen di area sekolah (meter)

// Rumus akurat menghitung jarak dua titik GPS di bumi
const hitungJarakMeter = (lat1, lon1, lat2, lon2) => {
  const R = 6371e3; // Jari-jari bumi dalam meter
  const p1 = lat1 * Math.PI / 180;
  const p2 = lat2 * Math.PI / 180;
  const dp = (lat2 - lat1) * Math.PI / 180;
  const dl = (lon2 - lon1) * Math.PI / 180;

  const a = Math.sin(dp / 2) * Math.sin(dp / 2) +
            Math.cos(p1) * Math.cos(p2) *
            Math.sin(dl / 2) * Math.sin(dl / 2);
  const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
  
  return R * c; // Hasil dalam meter
};

const dapatkanAlamatDariGPS = async (lat, lon) => {
  try {
    // 1. CEK RADIUS SEKOLAH TERLEBIH DAHULU
    const jarakKeSekolah = hitungJarakMeter(lat, lon, KOORDINAT_SEKOLAH.latitude, KOORDINAT_SEKOLAH.longitude);
    
    // Jika jarak kurang dari batas radius (misal 150 meter), paksa nama menjadi nama Sekolah
    if (jarakKeSekolah <= BATAS_RADIUS_METER) {
      return "SLB Dharma Asih Kraksaan"; 
    }

    // 2. JIKA DINAS LUAR (Di luar radius), baru lacak nama jalan/tempat pakai Peta
    const url = `https://nominatim.openstreetmap.org/reverse?format=jsonv2&lat=${lat}&lon=${lon}&zoom=18`;
    const res = await axios.get(url, { headers: { 'Accept-Language': 'id-ID' } });
    
    if (res.data && res.data.address) {
      const a = res.data.address;
      const namaTempat = a.amenity || a.building || a.office || a.tourism || a.shop || a.road || '';
      const desa = a.village || a.suburb || a.neighbourhood || '';
      const kec = a.city_district || a.county || '';
      const kota = a.city || a.town || '';
      
      const arrayAlamat = [];
      if (namaTempat) arrayAlamat.push(namaTempat);
      if (desa && !arrayAlamat.includes(desa)) arrayAlamat.push(desa);
      if (kec && !arrayAlamat.includes(kec)) arrayAlamat.push(kec);
      if (kota && !arrayAlamat.includes(kota)) arrayAlamat.push(kota);
      
      return arrayAlamat.filter(Boolean).join(', ') || "Lokasi tidak diketahui";
    }
    return `${lat}, ${lon}`;
  } catch (err) {
    return `${lat}, ${lon}`;
  }
};

const prosesAbsensiUser = async (jenis) => {
  isLoading.value = true;
  const teksJenis = jenis === 'masuk' ? 'MASUK' : 'PULANG';
  statusMessage.value = `Validasi wajah untuk absen ${teksJenis}...`;
  
  try {
    const resRef = await axios.get(`${apiBase}/face-descriptor/${currentUser.value.id_user}`);
    const dbDescriptorFloat32 = new Float32Array(JSON.parse(resRef.data.descriptor));

    const detections = await faceapi.detectSingleFace(videoElUser.value, new faceapi.TinyFaceDetectorOptions()).withFaceLandmarks().withFaceDescriptor();
    if (!detections) throw 'Wajah tidak terdeteksi. Posisikan ke tengah.';

    const distance = faceapi.euclideanDistance(detections.descriptor, dbDescriptorFloat32);
    if (distance > 0.5) throw 'Wajah TIDAK COCOK dengan referensi!';

    statusMessage.value = 'Wajah Cocok! Mengambil koordinat GPS...';
    const lokasi = await dapatkanGPS();

    const alamatLengkap = await dapatkanAlamatDariGPS(lokasi.latitude, lokasi.longitude);

    const canvas = document.createElement('canvas');
    canvas.width = videoElUser.value.videoWidth;
    canvas.height = videoElUser.value.videoHeight;
    canvas.getContext('2d', { willReadFrequently: true }).drawImage(videoElUser.value, 0, 0, canvas.width, canvas.height);

    const absRes = await axios.post(`${apiBase}/absen`, { 
      id_user: currentUser.value.id_user, 
      latitude: lokasi.latitude, longitude: lokasi.longitude,
      foto_absensi: canvas.toDataURL('image/jpeg', 0.8),
      confidence: Math.round((1 - distance) * 100),
      jenis_absen: jenis
    });
    
    statusMessage.value = 'SUKSES: ' + (absRes.data.message || `Absen ${teksJenis} direkam!`);
    statusColor.value = 'bg-success text-white shadow';
    statusIcon.value = 'fas fa-check-circle';
    fetchRiwayatUser();

  } catch (err) {
    statusMessage.value = err.response?.status === 404 ? 'GAGAL: Anda belum mendaftarkan wajah di Admin!' : 'GAGAL: ' + (err.response?.data?.error || err);
    statusColor.value = 'bg-danger-subtle text-danger-emphasis';
    statusIcon.value = 'fas fa-exclamation-circle';
  } finally {
    isLoading.value = false;
  }
};

// ================= FUNGSI EDIT & HAPUS LAPORAN ABSENSI =================

const bukaModalLaporan = (absen) => {
  // Masukkan data dari baris tabel yang diklik ke dalam form modal
  formLaporan.value = { 
    id: absen.id, 
    nama: absen.nama, 
    jam_masuk: absen.jam_masuk || '', 
    jam_keluar: absen.jam_keluar || '', 
    status: absen.status 
  };
  showModalLaporan.value = true; // Tampilkan pop-up modal
};

const simpanLaporan = async () => {
  try {
    await axios.put(`${apiBase}/laporan/${formLaporan.value.id}`, {
      jam_masuk: formLaporan.value.jam_masuk,
      jam_keluar: formLaporan.value.jam_keluar,
      status: formLaporan.value.status
    });
    showToast('success', 'Data absensi berhasil diperbarui.');
    showModalLaporan.value = false;
    fetchLaporan();
  } catch (err) {
    Swal.fire('Gagal!', err.response?.data?.error || err.message, 'error');
  }
};

const hapusLaporan = async (id) => {
  const result = await Swal.fire({
    title: 'Hapus Riwayat Absensi?',
    text: 'Data kehadiran ini akan dihapus secara permanen.',
    icon: 'warning',
    showCancelButton: true,
    confirmButtonColor: '#d33',
    cancelButtonColor: '#6c757d',
    confirmButtonText: 'Ya, Hapus!',
    cancelButtonText: 'Batal'
  });

  if (result.isConfirmed) {
    try {
      await axios.delete(`${apiBase}/laporan/${id}`);
      showToast('success', 'Riwayat absensi dihapus.');
      fetchLaporan();
    } catch (err) {
      Swal.fire('Error!', 'Gagal menghapus riwayat.', 'error');
    }
  }
};

// ================= WATCHER & EXPORT =================
watch([currentView, adminTab], ([newView, newTab]) => {
  if (newView === 'dashboard' && currentUser.value.role === 'admin') {
    if (newTab === 'users') fetchUsers();
    if (newTab === 'laporan') fetchLaporan();
    fetchJadwal(); 
  }
});
watch([currentView, userTab], async ([newView, newTab]) => {
  if (newView === 'dashboard' && currentUser.value.role === 'user') {
    if (newTab === 'absen') {
      await nextTick();
      await muatModelAI(); 
      startKameraUser();
    } else if (newTab === 'riwayat') {
      stopKamera();
      fetchRiwayatUser();
    }
  } else stopKamera();
});

const exportPDF = () => {
  const doc = new jsPDF();
  doc.setFontSize(16); 
  doc.text("Laporan Kehadiran Karyawan / Guru", 14, 20);
  
  autoTable(doc, {
    head: [['Tanggal', 'Nama Lengkap', 'Masuk', 'Pulang', 'Status', 'Lokasi/Alamat']],
    body: laporanAbsensi.value.map(i => [
      i.tanggal, 
      i.nama, 
      i.jam_masuk || '-',
      i.jam_keluar || '-',
      i.status,
      // Masukkan alamat, jika masih proses atau gagal, tampilkan tidak terdata
      i.alamat && !i.alamat.includes('Melacak') ? i.alamat : 'Tidak terdata' 
    ]), 
    startY: 30,
    styles: { fontSize: 9 }, // Perkecil font sedikit agar semua kolom muat
    columnStyles: { 
      5: { cellWidth: 60 } // Lebarkan khusus kolom alamat agar rapi
    }
  });
  
  doc.save("Laporan_Absensi.pdf");
};

const exportExcel = () => {
  // Mapping ulang array agar header tabel Excel menggunakan Bahasa Indonesia yang rapi
  // dan membuang kolom tidak penting (seperti ID atau koordinat mentah)
  const dataExport = laporanAbsensi.value.map(i => ({
    "Tanggal": i.tanggal,
    "Nama Lengkap": i.nama,
    "Jam Masuk": i.jam_masuk || '-',
    "Jam Pulang": i.jam_keluar || '-',
    "Status": i.status,
    "Lokasi / Alamat": i.alamat && !i.alamat.includes('Melacak') ? i.alamat : 'Tidak terdata'
  }));

  const ws = XLSX.utils.json_to_sheet(dataExport);
  
  // Mengatur kelebaran sel (kolom) di Excel agar tidak berantakan
  const wscols = [
    {wch: 15}, // Tanggal (A)
    {wch: 25}, // Nama (B)
    {wch: 12}, // Jam Masuk (C)
    {wch: 12}, // Jam Pulang (D)
    {wch: 12}, // Status (E)
    {wch: 50}  // Lokasi/Alamat (F)
  ];
  ws['!cols'] = wscols;

  const wb = XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb, ws, "Laporan Kehadiran");
  XLSX.writeFile(wb, "Laporan_Absensi.xlsx");
};
</script>

<style>
/* Impor CDNs */
@import url('https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css');
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css');
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&display=swap');

:root {
  --primary: #008751; 
  --primary-hover: #00683c;
  --secondary: #f8f9fa;
  --light-blue: #f0f7f4; 
}

body { font-family: 'Nunito', sans-serif; background-color: #f8fdf9; color: #333; margin: 0; padding: 0; }
.text-primary { color: var(--primary) !important; }
.bg-primary { background-color: var(--primary) !important; }
.btn-primary { background-color: var(--primary); border-color: var(--primary); }
.btn-primary:hover { background-color: var(--primary-hover); border-color: var(--primary-hover); }
.btn-outline-primary { color: var(--primary); border-color: var(--primary); }
.btn-outline-primary:hover { background-color: var(--primary); color: white; }
.bg-primary-subtle { background-color: #d1f0e1 !important; }
.bg-light-blue { background-color: var(--light-blue); }
.fw-extrabold { font-weight: 800; }

.fade-in-up { animation: fadeInUp 0.6s cubic-bezier(0.16, 1, 0.3, 1) both; }
@keyframes fadeInUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

.camera-container {
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
  border-radius: 15px;
  overflow: hidden;
  background-color: #000;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}
.camera-video {
  width: 100%;
  height: auto;
  aspect-ratio: 4/3;
  object-fit: cover;
}

/* Responsive Tabel (Bisa di-swipe kiri-kanan di layar kecil) */
.table-wrapper {
  overflow-x: auto;
  -webkit-overflow-scrolling: touch; /* Halus di iOS */
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}
.table {
  min-width: 700px; /* Cegah kolom tergencet di HP */
  margin-bottom: 0;
}

/* Responsive Menu Tabs (Menu melayang bisa digeser di HP) */
.mobile-scroll-nav {
  display: flex;
  flex-wrap: nowrap;
  overflow-x: auto;
  overflow-y: hidden;
  white-space: nowrap;
  -webkit-overflow-scrolling: touch;
  padding-bottom: 10px;
  scrollbar-width: none; /* Sembunyikan scrollbar di Firefox */
}
.mobile-scroll-nav::-webkit-scrollbar {
  display: none; /* Sembunyikan scrollbar di Chrome/Safari */
}
.mobile-scroll-nav .nav-item {
  flex: 0 0 auto;
}

/* Tampilan Modal Kustom ala Vue */
.custom-modal-overlay {
  display: block; 
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(3px);
}

.custom-link:hover {
  color: #198754 !important; /* Warna hijau Bootstrap */
  transition: 0.3s;
}
.transition-hover:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.1) !important;
  transition: all 0.3s ease;
}

.nav-pills .nav-link { transition: all 0.3s ease; border: 1px solid transparent; }
.nav-pills .nav-link.active { box-shadow: 0 4px 10px rgba(0, 135, 81, 0.2); }
.cursor-pointer { cursor: pointer; }
.scan-line { position: absolute; top: 0; left: 0; width: 100%; height: 5px; background: rgba(0, 135, 81, 0.7); box-shadow: 0 0 10px rgba(0, 135, 81, 1); animation: scan 2s infinite linear; }
@keyframes scan { 0% { top: 0%; } 50% { top: 100%; } 100% { top: 0%; } }
</style>