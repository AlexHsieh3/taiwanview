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
  <div class="min-h-screen flex flex-col">
    <!-- Sticky Header -->
    <header class="fixed top-0 left-0 right-0 z-50 w-full border-b border-sky-100 glass-nav transition-all duration-300">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-20">
          <!-- Logo -->
          <RouterLink to="/" class="flex items-center gap-3" @click="closeMenu">
            <div class="size-10 text-sky-500 flex items-center justify-center rounded-full bg-sky-50">
              <span class="material-symbols-outlined text-3xl">directions_bus</span>
            </div>
            <div>
              <h1 class="text-xl font-black text-slate-800 tracking-tight leading-none">大視界</h1>
              <p class="text-xs text-slate-500 font-medium tracking-wider">遊覽車有限公司</p>
            </div>
          </RouterLink>

          <!-- Desktop Navigation -->
          <nav class="hidden md:flex items-center gap-8">
            <RouterLink to="/" class="text-slate-600 hover:text-sky-500 font-medium text-sm transition-colors">首頁</RouterLink>
            <a href="#about" class="text-slate-600 hover:text-sky-500 font-medium text-sm transition-colors">公司簡介</a>
            <a href="#fleet" class="text-slate-600 hover:text-sky-500 font-medium text-sm transition-colors">車型簡介</a>
            <a href="#services" class="text-slate-600 hover:text-sky-500 font-medium text-sm transition-colors">服務項目</a>
            <a href="#contact" class="text-slate-600 hover:text-sky-500 font-medium text-sm transition-colors">聯絡我們</a>
          </nav>

          <!-- CTA Button -->
          <div class="hidden md:flex items-center">
            <a href="#contact" class="bg-sky-500 hover:bg-sky-600 text-white text-sm font-bold py-2.5 px-6 rounded-full shadow-lg shadow-sky-200 transition-all transform hover:-translate-y-0.5 flex items-center gap-2">
              <span class="material-symbols-outlined text-[20px]">calendar_month</span>
              立即預約
            </a>
          </div>

          <!-- Mobile Menu Button -->
          <div class="md:hidden flex items-center">
            <button @click="toggleMenu" class="text-slate-600 hover:text-sky-500 p-2">
              <span class="material-symbols-outlined text-3xl">{{ isMenuOpen ? 'close' : 'menu' }}</span>
            </button>
          </div>
        </div>

        <!-- Mobile Navigation -->
        <nav v-show="isMenuOpen" class="md:hidden pb-4 space-y-2">
          <RouterLink to="/" class="block py-2 px-4 text-slate-600 hover:bg-sky-50 hover:text-sky-500 rounded-lg font-medium" @click="closeMenu">首頁</RouterLink>
          <a href="#about" class="block py-2 px-4 text-slate-600 hover:bg-sky-50 hover:text-sky-500 rounded-lg font-medium" @click="closeMenu">公司簡介</a>
          <a href="#fleet" class="block py-2 px-4 text-slate-600 hover:bg-sky-50 hover:text-sky-500 rounded-lg font-medium" @click="closeMenu">車型簡介</a>
          <a href="#services" class="block py-2 px-4 text-slate-600 hover:bg-sky-50 hover:text-sky-500 rounded-lg font-medium" @click="closeMenu">服務項目</a>
          <a href="#contact" class="block py-2 px-4 text-slate-600 hover:bg-sky-50 hover:text-sky-500 rounded-lg font-medium" @click="closeMenu">聯絡我們</a>
          <a href="#contact" class="block py-3 px-4 bg-sky-500 text-white text-center rounded-lg font-bold mt-4" @click="closeMenu">立即預約</a>
        </nav>
      </div>
    </header>

    <!-- Main Content -->
    <main class="flex-1 pt-20">
      <RouterView />
    </main>

    <!-- Footer -->
    <footer class="bg-slate-900 text-slate-400 py-12 border-t border-slate-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
          <!-- Brand -->
          <div class="col-span-1">
            <div class="flex items-center gap-2 mb-4 text-white">
              <span class="material-symbols-outlined text-sky-500">directions_bus</span>
              <span class="font-bold text-lg">大視界</span>
            </div>
            <p class="text-sm leading-relaxed mb-4">
              專注於提供高品質的包車旅遊服務，讓每一位旅客都能享受安全、舒適、愉快的旅程。
            </p>
            <div class="flex gap-4">
              <a href="#" class="hover:text-white transition-colors text-xl">FB</a>
              <a href="#" class="hover:text-white transition-colors text-xl">LINE</a>
              <a href="#" class="hover:text-white transition-colors text-xl">IG</a>
            </div>
          </div>

          <!-- Quick Links -->
          <div>
            <h3 class="text-white font-bold mb-4">快速連結</h3>
            <ul class="space-y-2 text-sm">
              <li><a href="#about" class="hover:text-sky-500 transition-colors">關於我們</a></li>
              <li><a href="#fleet" class="hover:text-sky-500 transition-colors">車型介紹</a></li>
              <li><a href="#services" class="hover:text-sky-500 transition-colors">服務項目</a></li>
              <li><a href="#" class="hover:text-sky-500 transition-colors">最新消息</a></li>
            </ul>
          </div>

          <!-- Service Areas -->
          <div>
            <h3 class="text-white font-bold mb-4">服務地區</h3>
            <ul class="space-y-2 text-sm">
              <li>全台旅遊包車</li>
              <li>機場接送服務</li>
              <li>商務洽公接送</li>
              <li>婚紗外拍包車</li>
            </ul>
          </div>

          <!-- Company Info -->
          <div>
            <h3 class="text-white font-bold mb-4">公司資訊</h3>
            <ul class="space-y-2 text-sm">
              <li>統編：24348728</li>
              <li>電話：02-2954-8100</li>
              <li>傳真：02-2954-8101</li>
              <li>服務時間：09:00 - 18:00</li>
            </ul>
          </div>
        </div>

        <div class="border-t border-slate-800 pt-8 flex flex-col md:flex-row justify-between items-center gap-4 text-xs">
          <p>© {{ new Date().getFullYear() }} 大視界遊覽車有限公司. All rights reserved.</p>
          <div class="flex gap-4">
            <a href="#" class="hover:text-white">隱私權政策</a>
            <a href="#" class="hover:text-white">使用者條款</a>
          </div>
        </div>
      </div>
    </footer>

    <!-- Floating Action Button for Mobile -->
    <a href="tel:0919906715" class="md:hidden fixed bottom-6 right-6 w-14 h-14 bg-green-500 text-white rounded-full shadow-lg flex items-center justify-center z-50 animate-bounce">
      <span class="material-symbols-outlined text-3xl">call</span>
    </a>
  </div>
</template>

<style scoped>
/* 使用全域 glass-nav 樣式 */
</style>
