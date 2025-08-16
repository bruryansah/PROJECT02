<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { Link } from '@inertiajs/vue3'

const activeMenu = ref('beranda')

function setActiveMenu(menu: string) {
  activeMenu.value = menu
}

// Animation on scroll
onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in')
      }
    })
  }, {
    threshold: 0.1
  })

  document.querySelectorAll('.animate-on-scroll').forEach(el => {
    observer.observe(el)
  })
})
</script>

<template>
  <div class="welcome-page">
    <!-- Navbar -->
    <nav class="navbar">
      <div class="navbar-left">
        <img src="https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2022/03/LOGO-TAMSIS-MATERIAL-DESIGN.png" alt="Logo SMK Tamansiswa 2 Jakarta" class="logo" />
        <div class="brand">
          <span class="brand-title">SMK Tamansiswa 2 Jakarta</span>
          <span class="brand-subtitle">"Urip Mung Mampir Ngombe"</span>
        </div>
      </div>

      <ul class="nav-links">
        <li>
          <Link href="/" :class="{ active: activeMenu === 'beranda' }" @click="setActiveMenu('beranda')"> Beranda </Link>
        </li>
        <li>
          <Link href="/tentang" :class="{ active: activeMenu === 'tentang' }" @click="setActiveMenu('tentang')"> Tentang </Link>
        </li>
        <li>
          <Link href="/jurusan" :class="{ active: activeMenu === 'jurusan' }" @click="setActiveMenu('jurusan')"> Jurusan </Link>
        </li>
        <li>
          <Link href="/kontak" :class="{ active: activeMenu === 'kontak' }" @click="setActiveMenu('kontak')"> Kontak </Link>
        </li>
      </ul>

      <div class="auth-buttons">
        <Link href="/login" class="btn-login">Login</Link>
        <Link href="/register" class="btn-register">Register</Link>
      </div>
    </nav>

    <!-- Main Container -->
    <div class="main-container">
      <div class="breadcrumb">Beranda / {{ activeMenu }}</div>
      <h1 class="page-title animate-on-scroll">{{ activeMenu.charAt(0).toUpperCase() + activeMenu.slice(1) }}</h1>

      <div class="content">
        <!-- Banner with school motto -->
        <div class="banner animate-on-scroll">
          <div class="banner-content">
            <h2>Selamat Datang di SMK Tamansiswa 2 Jakarta</h2>
            <p>Mendidik dengan Sistem Among, Menciptakan Generasi Mandiri dan Berkarakter</p>
          </div>
        </div>

        <div class="content-grid">
          <div class="left-content">
            <div class="big-box animate-on-scroll">
              <h3>Visi Sekolah</h3>
              <p>"Menjadi lembaga pendidikan kejuruan yang unggul dalam menghasilkan lulusan berkompeten, berkarakter, dan berwawasan global berdasarkan nilai-nilai Tamansiswa."</p>
              
              <h3>Misi Sekolah</h3>
              <ul>
                <li>Menyelenggarakan pendidikan kejuruan yang berkualitas</li>
                <li>Mengembangkan potensi siswa secara holistik</li>
                <li>Menanamkan nilai-nilai Tamansiswa dalam pembelajaran</li>
                <li>Membangun kerjasama dengan dunia industri</li>
              </ul>
            </div>

            <div class="news-section animate-on-scroll">
              <h3>Berita Terkini</h3>
              <div class="news-grid">
                <div class="news-card">
                  <div class="news-image"></div>
                  <h4>Penerimaan Peserta Didik Baru 2024</h4>
                  <p>Pendaftaran dibuka mulai 1 Maret 2024</p>
                </div>
                <div class="news-card">
                  <div class="news-image"></div>
                  <h4>Workshop Kewirausahaan</h4>
                  <p>Pelatihan untuk siswa kelas XII</p>
                </div>
              </div>
            </div>
          </div>

          <div class="right-sidebar">
            <div class="small-box animate-on-scroll">
              <h3>Jurusan Kami</h3>
              <ul>
                <li>Rekayasa Perangkat Lunak</li>
                <li>Teknik Komputer Jaringan</li>
                <li>Teknik Instalasi Tenaga Listrik</li>
                <li>Teknik Permesinan</li>
                <li>Teknik Kendaraan Ringan</li>
                <li>Teknik Sepeda Motor</li>
              </ul>
            </div>
            <div class="small-box animate-on-scroll">
              <h3>Info Cepat</h3>
              <div class="quick-info">
                <div class="info-item">
                  <strong>Alamat:</strong>
                  <p>Jl. Garuda No. 44, Kemayoran, Jakarta Pusat</p>
                </div>
                <div class="info-item">
                  <strong>Telepon:</strong>
                  <p>(021) 420-8765</p>
                </div>
                <div class="info-item">
                  <strong>Email:</strong>
                  <p>info@smktamansiswa2jakarta.sch.id</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
      <div class="footer-content">
        <div class="footer-left">
          <img
            src="https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2022/03/LOGO-TAMSIS-MATERIAL-DESIGN.png"
            alt="Logo SMK Tamansiswa 2 Jakarta"
            class="footer-logo"
          />
          <span class="footer-text">© 2024 SMK TAMANSISWA 2 JAKARTA | "Ing Ngarsa Sung Tuladha, Ing Madya Mangun Karsa, Tut Wuri Handayani"</span>
        </div>
        <div class="footer-right">
          <a href="https://facebook.com/smktamansiswa2jakarta" class="social-link" target="_blank">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="social-icon">
              <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
            </svg>
          </a>
          <a href="https://instagram.com/smktamansiswa2jakarta" class="social-link" target="_blank">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="social-icon">
              <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
              <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
              <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
            </svg>
          </a>
          <a href="https://youtube.com/@smktamansiswa2jakarta375?si=XuMQeADTidosYWLq" class="social-link" target="_blank">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="social-icon">
              <path d="M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z"></path>
              <polygon points="9.75 15.02 15.5 11.75 9.75 8.48 9.75 15.02"></polygon>
            </svg>
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.welcome-page {
    min-height: 100vh;
    background-color: #f5f5f5;
    display: flex;
    flex-direction: column;
}

/* ====== Animations ====== */
.animate-on-scroll {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

.animate-on-scroll.animate-in {
  opacity: 1;
  transform: translateY(0);
}

/* Delay animations for staggered effect */
.animate-on-scroll:nth-child(1) { transition-delay: 0.1s; }
.animate-on-scroll:nth-child(2) { transition-delay: 0.2s; }
.animate-on-scroll:nth-child(3) { transition-delay: 0.3s; }
.animate-on-scroll:nth-child(4) { transition-delay: 0.4s; }

/* ====== Navbar ====== */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: white;
    padding: 12px 24px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.08);
    position: sticky;
    top: 0;
    z-index: 100;
    transition: all 0.3s ease;
}

.navbar.scrolled {
    padding: 8px 24px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.navbar-left {
    display: flex;
    align-items: center;
    gap: 12px;
}

/* Logo Styling */
.logo {
    width: 40px;
    height: 40px;
    object-fit: contain;
    transition: transform 0.3s ease;
}

.logo:hover {
    transform: rotate(15deg);
}

.brand {
    display: flex;
    flex-direction: column;
}

.brand-title {
    font-weight: 600;
    font-size: 18px;
    color: #111827;
}

.brand-subtitle {
    font-size: 14px;
    color: #6b7280;
    font-style: italic;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 130px;
    margin: 0;
    padding: 0;
}

.nav-links li {
    position: relative;
    color: #6b7280;
    font-size: 16px;
    cursor: pointer;
    font-weight: 500;
    transition: color 0.2s;
}

.nav-links li:hover {
    color: #111827;
}

.nav-links li.active {
    color: #111827;
    font-weight: 600;
}

.nav-links li.active::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 100%;
    height: 2px;
    background-color: #2563eb;
    animation: underline 0.3s ease-out;
}

@keyframes underline {
    from { width: 0; }
    to { width: 100%; }
}

.auth-buttons {
    display: flex;
    gap: 12px;
}

.btn-login {
    padding: 8px 16px;
    border: 2px solid #2563eb;
    background: transparent;
    color: #2563eb;
    border-radius: 6px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
}

.btn-login:hover {
    background-color: #eff6ff;
    transform: translateY(-2px);
}

.btn-register {
    padding: 8px 16px;
    background: #2563eb;
    color: white;
    border: 2px solid #2563eb;
    border-radius: 6px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
}

.btn-register:hover {
    background-color: #1d4ed8;
    border-color: #1d4ed8;
    transform: translateY(-2px);
}

/* ====== Main Container ====== */
.main-container {
    flex: 1;
    max-width: 1200px;
    margin: 0 auto;
    width: 100%;
    padding: 0 24px;
}

/* ====== Breadcrumb & Title ====== */
.breadcrumb {
    font-size: 14px;
    margin: 24px 0 8px 0;
    color: #6b7280;
}

.page-title {
    margin: 0 0 24px 0;
    font-size: 32px;
    font-weight: 700;
    color: #111827;
    position: relative;
    display: inline-block;
}

.page-title::after {
    content: '';
    position: absolute;
    bottom: -8px;
    left: 0;
    width: 50px;
    height: 4px;
    background-color: #2563eb;
    border-radius: 2px;
}

/* ====== Content ====== */
.content {
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.banner {
    height: 300px;
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2022/03/gedung-sekolah.jpg');
    background-size: cover;
    background-position: center;
    border-radius: 12px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    text-align: center;
    padding: 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.banner-content h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.8);
}

.banner-content p {
    font-size: 1.2rem;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
}

.content-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 24px;
}

.left-content .big-box {
    min-height: 300px;
    background: white;
    border-radius: 12px;
    padding: 24px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.big-box h3 {
    color: #2563eb;
    margin-bottom: 16px;
    font-size: 1.5rem;
}

.big-box p, .big-box ul {
    margin-bottom: 20px;
    line-height: 1.6;
    color: #4b5563;
}

.big-box ul {
    padding-left: 20px;
}

.big-box li {
    margin-bottom: 8px;
}

.news-section {
    margin-top: 30px;
}

.news-section h3 {
    color: #2563eb;
    margin-bottom: 16px;
    font-size: 1.5rem;
}

.news-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
}

.news-card {
    background: white;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.news-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
}

.news-image {
    height: 150px;
    background: #d1d5db;
    background-size: cover;
    background-position: center;
}

.news-card:nth-child(1) .news-image {
    background-image: url('https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2023/05/ppdb-2023.jpg');
}

.news-card:nth-child(2) .news-image {
    background-image: url('https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2023/04/workshop-kewirausahaan.jpg');
}

.news-card h4 {
    padding: 12px 16px 0;
    color: #111827;
}

.news-card p {
    padding: 8px 16px 16px;
    color: #6b7280;
    font-size: 0.9rem;
}

.right-sidebar {
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.small-box {
    min-height: 200px;
    background: white;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.small-box h3 {
    color: #2563eb;
    margin-bottom: 16px;
    font-size: 1.3rem;
}

.small-box ul {
    list-style: none;
}

.small-box li {
    padding: 8px 0;
    border-bottom: 1px solid #e5e7eb;
    color: #4b5563;
}

.small-box li:last-child {
    border-bottom: none;
}

.small-box li::before {
    content: '•';
    color: #2563eb;
    display: inline-block;
    width: 1em;
    margin-left: -1em;
}

.quick-info {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.info-item {
    background: #f9fafb;
    padding: 12px;
    border-radius: 8px;
}

.info-item strong {
    color: #111827;
    display: block;
    margin-bottom: 4px;
}

.info-item p {
    color: #6b7280;
    font-size: 0.9rem;
}

/* ====== Footer ====== */
.footer {
    margin-top: 64px;
    background: white;
    border-top: 1px solid #e5e7eb;
}

.footer-content {
    max-width: 1200px;
    margin: 0 auto;
    padding: 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.footer-left {
    display: flex;
    align-items: center;
    gap: 12px;
    max-width: 70%;
}

/* Footer Logo */
.footer-logo {
    width: 32px;
    height: 32px;
    object-fit: contain;
    flex-shrink: 0;
}

.footer-text {
    font-size: 14px;
    color: #6b7280;
    line-height: 1.5;
}

.footer-right {
    display: flex;
    gap: 16px;
}

.social-link {
    color: #6b7280;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: #f3f4f6;
}

.social-link:hover {
    color: white;
    background: #2563eb;
    transform: translateY(-3px);
}

.social-icon {
    width: 20px;
    height: 20px;
}

/* ====== Responsive ====== */
@media (max-width: 1024px) {
    .nav-links {
        gap: 30px;
    }
    
    .banner-content h2 {
        font-size: 2rem;
    }
    
    .banner-content p {
        font-size: 1rem;
    }
}

@media (max-width: 768px) {
    .navbar {
        flex-direction: column;
        gap: 16px;
        padding: 16px;
    }

    .nav-links {
        flex-wrap: wrap;
        justify-content: center;
        gap: 16px 30px;
    }
    
    .auth-buttons {
        margin-top: 10px;
    }

    .content-grid {
        grid-template-columns: 1fr;
    }
    
    .right-sidebar {
        flex-direction: row;
        flex-wrap: wrap;
    }
    
    .small-box {
        flex: 1 1 300px;
    }
    
    .banner {
        height: 250px;
    }
    
    .banner-content h2 {
        font-size: 1.8rem;
    }
    
    .footer-content {
        flex-direction: column;
        gap: 24px;
        text-align: center;
    }
    
    .footer-left {
        flex-direction: column;
        max-width: 100%;
    }
}

@media (max-width: 480px) {
    .brand-title {
        font-size: 16px;
    }
    
    .brand-subtitle {
        font-size: 12px;
    }
    
    .banner {
        height: 200px;
    }
    
    .banner-content h2 {
        font-size: 1.5rem;
    }
    
    .banner-content p {
        font-size: 0.9rem;
    }
    
    .page-title {
        font-size: 1.8rem;
    }
    
    .small-box {
        flex: 1 1 100%;
    }
}
</style>