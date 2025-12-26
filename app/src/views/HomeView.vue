<script setup lang="ts">
import { ref } from 'vue'

const features = ref([
  {
    icon: '🏔️',
    title: '自然景觀',
    description: '從高山到海岸，探索台灣壯麗的自然風光'
  },
  {
    icon: '🏛️',
    title: '文化遺產',
    description: '深入了解台灣豐富的歷史文化與傳統藝術'
  },
  {
    icon: '🍜',
    title: '美食饗宴',
    description: '品嚐道地台灣美食，從夜市小吃到精緻料理'
  },
  {
    icon: '🎭',
    title: '民俗節慶',
    description: '體驗獨特的台灣節慶活動與民俗傳統'
  }
])

const contactForm = ref({
  name: '',
  email: '',
  message: ''
})

const handleSubmit = () => {
  console.log('表單提交:', contactForm.value)
  alert('感謝您的訊息！我們會盡快回覆您。')
  contactForm.value = { name: '', email: '', message: '' }
}
</script>

<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">探索台灣之美</h1>
        <p class="hero-subtitle">發現這座島嶼的無限魅力，從山巔到海角，從古蹟到現代</p>
        <div class="hero-buttons">
          <a href="#features" class="btn btn-primary">開始探索</a>
          <a href="#contact" class="btn btn-secondary">聯絡我們</a>
        </div>
      </div>
      <div class="hero-decoration">
        <div class="floating-icon" style="--delay: 0s">🌸</div>
        <div class="floating-icon" style="--delay: 1s">🏯</div>
        <div class="floating-icon" style="--delay: 2s">🌊</div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="section features">
      <div class="container">
        <h2 class="section-title">探索精彩內容</h2>
        <p class="section-subtitle">TaiwanView 帶您深入了解台灣的每一個精彩角落</p>

        <div class="features-grid">
          <div v-for="feature in features" :key="feature.title" class="feature-card">
            <div class="feature-icon">{{ feature.icon }}</div>
            <h3 class="feature-title">{{ feature.title }}</h3>
            <p class="feature-desc">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
      <div class="container">
        <div class="about-content">
          <div class="about-text">
            <h2 class="section-title" style="text-align: left">關於 TaiwanView</h2>
            <p>
              TaiwanView
              致力於向世界展示台灣的獨特魅力。我們透過精心策劃的內容，帶領您深入探索這座美麗島嶼的每一個角落。
            </p>
            <p>
              無論您是想了解台灣的自然景觀、歷史文化、美食特色，還是想規劃一趟難忘的旅程，TaiwanView
              都能為您提供最完整、最在地的資訊。
            </p>
            <RouterLink to="/about" class="btn btn-primary">了解更多</RouterLink>
          </div>
          <div class="about-image">
            <div class="image-placeholder">
              <span>🗺️</span>
              <p>台灣地圖</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact">
      <div class="container">
        <h2 class="section-title">聯絡我們</h2>
        <p class="section-subtitle">有任何問題或建議？歡迎與我們聯繫</p>

        <form class="contact-form" @submit.prevent="handleSubmit">
          <div class="form-group">
            <label for="name">姓名</label>
            <input
              id="name"
              v-model="contactForm.name"
              type="text"
              placeholder="請輸入您的姓名"
              required
            />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input
              id="email"
              v-model="contactForm.email"
              type="email"
              placeholder="請輸入您的 Email"
              required
            />
          </div>
          <div class="form-group">
            <label for="message">訊息</label>
            <textarea
              id="message"
              v-model="contactForm.message"
              placeholder="請輸入您的訊息"
              rows="5"
              required
            ></textarea>
          </div>
          <button type="submit" class="btn btn-primary">送出訊息</button>
        </form>
      </div>
    </section>
  </div>
</template>

<style scoped>
/* Hero Section */
.hero {
  min-height: calc(100vh - 70px);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: linear-gradient(135deg, #e8f5e9 0%, #c8e6c9 50%, #a5d6a7 100%);
  position: relative;
  overflow: hidden;
  padding: 2rem;
}

.hero-content {
  position: relative;
  z-index: 1;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  color: var(--dark-color);
  margin-bottom: 1rem;
  animation: fadeInUp 0.8s ease;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: var(--text-light);
  max-width: 600px;
  margin: 0 auto 2rem;
  animation: fadeInUp 0.8s ease 0.2s backwards;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  animation: fadeInUp 0.8s ease 0.4s backwards;
}

.hero-decoration {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
}

.floating-icon {
  position: absolute;
  font-size: 3rem;
  animation: float 6s ease-in-out infinite;
  animation-delay: var(--delay);
  opacity: 0.3;
}

.floating-icon:nth-child(1) {
  top: 20%;
  left: 10%;
}

.floating-icon:nth-child(2) {
  top: 60%;
  right: 15%;
}

.floating-icon:nth-child(3) {
  bottom: 20%;
  left: 20%;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Features Section */
.features {
  background: white;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: var(--light-color);
  padding: 2rem;
  border-radius: 16px;
  text-align: center;
  transition: var(--transition);
}

.feature-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-lg);
}

.feature-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.feature-title {
  font-size: 1.25rem;
  color: var(--dark-color);
  margin-bottom: 0.5rem;
}

.feature-desc {
  color: var(--text-light);
  font-size: 0.95rem;
}

/* About Section */
.about {
  background: var(--light-color);
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.about-text p {
  color: var(--text-light);
  margin-bottom: 1.5rem;
  line-height: 1.8;
}

.about-image {
  display: flex;
  justify-content: center;
}

.image-placeholder {
  width: 300px;
  height: 300px;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  border-radius: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: white;
}

.image-placeholder span {
  font-size: 5rem;
}

.image-placeholder p {
  margin-top: 1rem;
  font-weight: 600;
}

/* Contact Section */
.contact {
  background: white;
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: var(--dark-color);
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.75rem 1rem;
  border: 2px solid var(--border-color);
  border-radius: 8px;
  font-size: 1rem;
  transition: var(--transition);
  font-family: inherit;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--primary-color);
}

.contact-form .btn {
  width: 100%;
}

/* Responsive */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }

  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .about-text {
    text-align: center;
  }

  .about-text .section-title {
    text-align: center !important;
  }

  .image-placeholder {
    width: 200px;
    height: 200px;
  }

  .image-placeholder span {
    font-size: 3rem;
  }
}
</style>
