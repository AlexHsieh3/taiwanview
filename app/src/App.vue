<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <div class="app-wrapper">
    <!-- 導航列 -->
    <header class="navbar">
      <div class="container navbar-container">
        <RouterLink to="/" class="logo" @click="closeMenu">
          <span class="logo-icon">🌏</span>
          <span class="logo-text">TaiwanView</span>
        </RouterLink>

        <button class="menu-toggle" @click="toggleMenu" :aria-expanded="isMenuOpen">
          <span class="hamburger" :class="{ active: isMenuOpen }"></span>
        </button>

        <nav class="nav-menu" :class="{ active: isMenuOpen }">
          <RouterLink to="/" class="nav-link" @click="closeMenu">首頁</RouterLink>
          <RouterLink to="/about" class="nav-link" @click="closeMenu">關於我們</RouterLink>
          <a href="#features" class="nav-link" @click="closeMenu">功能特色</a>
          <a href="#contact" class="nav-link" @click="closeMenu">聯絡我們</a>
        </nav>
      </div>
    </header>

    <!-- 主要內容 -->
    <main class="main-content">
      <RouterView />
    </main>

    <!-- 頁尾 -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-brand">
            <span class="logo-icon">🌏</span>
            <span class="logo-text">TaiwanView</span>
            <p class="footer-desc">探索台灣之美，發現在地故事</p>
          </div>
          <div class="footer-links">
            <h4>快速連結</h4>
            <RouterLink to="/">首頁</RouterLink>
            <RouterLink to="/about">關於我們</RouterLink>
          </div>
          <div class="footer-contact">
            <h4>聯絡資訊</h4>
            <p>Email: contact@taiwanview.com</p>
          </div>
        </div>
        <div class="footer-bottom">
          <p>&copy; {{ new Date().getFullYear() }} TaiwanView. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.app-wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* 導航列 */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: var(--shadow);
  z-index: 1000;
}

.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 1.5rem;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary-color);
}

.logo:hover {
  color: var(--primary-light);
}

.logo-icon {
  font-size: 1.8rem;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  font-weight: 500;
  color: var(--text-color);
  padding: 0.5rem 0;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--primary-color);
  transition: var(--transition);
}

.nav-link:hover::after,
.nav-link.router-link-active::after {
  width: 100%;
}

.nav-link.router-link-active {
  color: var(--primary-color);
}

/* 漢堡選單按鈕 */
.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
}

.hamburger {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--text-color);
  position: relative;
  transition: var(--transition);
}

.hamburger::before,
.hamburger::after {
  content: '';
  position: absolute;
  width: 24px;
  height: 2px;
  background: var(--text-color);
  transition: var(--transition);
}

.hamburger::before {
  top: -8px;
}

.hamburger::after {
  top: 8px;
}

.hamburger.active {
  background: transparent;
}

.hamburger.active::before {
  top: 0;
  transform: rotate(45deg);
}

.hamburger.active::after {
  top: 0;
  transform: rotate(-45deg);
}

/* 主要內容 */
.main-content {
  flex: 1;
  margin-top: 70px;
}

/* 頁尾 */
.footer {
  background: var(--dark-color);
  color: white;
  padding: 3rem 0 1rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer-brand .logo-icon,
.footer-brand .logo-text {
  font-size: 1.5rem;
}

.footer-desc {
  margin-top: 0.5rem;
  color: rgba(255, 255, 255, 0.7);
}

.footer-links h4,
.footer-contact h4 {
  margin-bottom: 1rem;
  color: var(--secondary-color);
}

.footer-links a {
  display: block;
  color: rgba(255, 255, 255, 0.7);
  margin-bottom: 0.5rem;
}

.footer-links a:hover {
  color: white;
}

.footer-contact p {
  color: rgba(255, 255, 255, 0.7);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 1rem;
  text-align: center;
  color: rgba(255, 255, 255, 0.5);
}

/* 響應式設計 */
@media (max-width: 768px) {
  .menu-toggle {
    display: block;
  }

  .nav-menu {
    position: fixed;
    top: 70px;
    left: 0;
    right: 0;
    background: white;
    flex-direction: column;
    padding: 1rem;
    gap: 0;
    box-shadow: var(--shadow);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: var(--transition);
  }

  .nav-menu.active {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .nav-link {
    padding: 1rem;
    width: 100%;
    text-align: center;
    border-bottom: 1px solid var(--border-color);
  }

  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
}
</style>
