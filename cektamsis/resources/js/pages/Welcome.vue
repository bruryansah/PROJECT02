<script setup lang="ts">
import { ref } from 'vue';

const activeMenu = ref('beranda');

function setActiveMenu(menu: string) {
    activeMenu.value = menu;
}
</script>

<template>
    <div class="welcome-page">
        <!-- Navbar -->
        <nav class="navbar">
            <div class="navbar-left">
                <img src="https://smktamansiswa2jakarta.sch.id/wp-content/uploads/2022/03/LOGO-TAMSIS-MATERIAL-DESIGN.png" alt="Logo" class="logo" />
                <div class="brand">
                    <span class="brand-title">Check</span>
                    <span class="brand-subtitle">Tharnsies</span>
                </div>
            </div>

            <ul class="nav-links">
                <li :class="{ active: activeMenu === 'beranda' }" @click="setActiveMenu('beranda')">Beranda</li>
                <li :class="{ active: activeMenu === 'tentang' }" @click="setActiveMenu('tentang')">Tentang</li>
                <li :class="{ active: activeMenu === 'fitur' }" @click="setActiveMenu('fitur')">Fitur</li>
                <li :class="{ active: activeMenu === 'kontak' }" @click="setActiveMenu('kontak')">Kontak</li>
            </ul>

            <div class="auth-buttons">
                <!-- Link dari Inertia -->
                <a :href="'/login'" class="btn-login">Login</a>
                <a href="/register" class="btn-register">Daftar</a>
            </div>
        </nav>

        <!-- Main Container -->
        <div class="main-container">
            <div class="breadcrumb">Beranda / {{ activeMenu }}</div>
            <h1 class="page-title">{{ activeMenu.charAt(0).toUpperCase() + activeMenu.slice(1) }}</h1>

            <div class="content">
                <div class="banner"></div>

                <div class="content-grid">
                    <div class="left-content">
                        <div class="big-box"></div>
                    </div>

                    <div class="right-sidebar">
                        <div class="small-box"></div>
                        <div class="small-box"></div>
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
                        alt="Logo"
                        class="footer-logo"
                    />
                    <span class="footer-text">© SMK TAMANSISWA 2 JAKARTA | RPL</span>
                </div>
                <div class="footer-right">
                    <a href="#" class="social-link">
                        <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path
                                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                            />
                        </svg>
                    </a>
                    <a href="#" class="social-link">
                        <!-- FB -->
                        <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
                            <path
                                d="M24 12.073c0-6.627-5.373-12-12-12S0 5.446 0 12.073c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953h-1.514c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                            />
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
}

.welcome-page {
    min-height: 100vh;
    background-color: #f5f5f5;
    display: flex;
    flex-direction: column;
}

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
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 130px;
    margin: 0;
    padding: 0;
}

.nav-links li {
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
}

.btn-login:hover {
    background-color: #eff6ff;
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
}

.btn-register:hover {
    background-color: #1d4ed8;
    border-color: #1d4ed8;
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
}

/* ====== Content ====== */
.content {
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.banner {
    height: 250px;
    background: #d1d5db;
    border-radius: 12px;
    width: 100%;
}

.content-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 24px;
}

.left-content .big-box {
    height: 200px;
    background: #d1d5db;
    border-radius: 12px;
}

.right-sidebar {
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.small-box {
    height: 88px;
    background: #d1d5db;
    border-radius: 12px;
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
}

/* Footer Logo */
.footer-logo {
    width: 32px;
    height: 32px;
    object-fit: contain;
}

.footer-text {
    font-size: 14px;
    color: #6b7280;
}

.footer-right {
    display: flex;
    gap: 16px;
}

.social-link {
    color: #6b7280;
    transition: color 0.2s;
}

.social-link:hover {
    color: #111827;
}

.social-icon {
    width: 20px;
    height: 20px;
}

/* ====== Responsive ====== */
@media (max-width: 768px) {
    .navbar {
        flex-direction: column;
        gap: 16px;
        padding: 16px;
    }

    .nav-links {
        gap: 16px;
    }

    .content-grid {
        grid-template-columns: 1fr;
    }

    .footer-content {
        flex-direction: column;
        gap: 16px;
        text-align: center;
    }
}
</style>
