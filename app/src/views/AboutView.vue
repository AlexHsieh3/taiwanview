<template>
  <div class="about-page">
    <section class="about-hero">
      <div class="container">
        <h1>關於 TaiwanView</h1>
        <p>致力於向世界展示台灣的獨特魅力</p>
      </div>
    </section>

    <section class="section about-mission">
      <div class="container">
        <div class="mission-content">
          <div class="mission-text">
            <h2>我們的使命</h2>
            <p>
              TaiwanView 創立於對台灣這片土地的熱愛。我們相信，台灣不僅是一個地理位置，更是一個充滿故事、文化和溫暖人情的美麗島嶼。
            </p>
            <p>
              我們的目標是透過數位平台，讓更多人認識台灣的多元面貌：從壯麗的自然景觀到深厚的文化底蘊，從傳統的民俗藝術到現代的創新發展。
            </p>
          </div>
          <div class="mission-icon">
            <span>🌏</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section about-values">
      <div class="container">
        <h2 class="section-title">核心價值</h2>
        <div class="values-grid">
          <div class="value-card">
            <span class="value-icon">🎯</span>
            <h3>真實呈現</h3>
            <p>提供最真實、最在地的台灣資訊</p>
          </div>
          <div class="value-card">
            <span class="value-icon">💡</span>
            <h3>創新思維</h3>
            <p>用現代方式傳承傳統文化</p>
          </div>
          <div class="value-card">
            <span class="value-icon">🤝</span>
            <h3>連結世界</h3>
            <p>讓台灣與世界建立更緊密的聯繫</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section about-cta">
      <div class="container">
        <h2>一起探索台灣</h2>
        <p>加入我們，發現更多台灣的精彩故事</p>
        <RouterLink to="/" class="btn btn-primary">開始探索</RouterLink>
      </div>
    </section>
  </div>
</template>

<style scoped>
.about-hero {
  background: linear-gradient(135deg, var(--primary-color), var(--primary-light));
  color: white;
  padding: 6rem 0;
  text-align: center;
}

.about-hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.about-hero p {
  font-size: 1.25rem;
  opacity: 0.9;
}

.about-mission {
  background: white;
}

.mission-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  align-items: center;
}

.mission-text h2 {
  font-size: 2rem;
  color: var(--dark-color);
  margin-bottom: 1.5rem;
}

.mission-text p {
  color: var(--text-light);
  line-height: 1.8;
  margin-bottom: 1rem;
}

.mission-icon {
  display: flex;
  justify-content: center;
  align-items: center;
}

.mission-icon span {
  font-size: 8rem;
}

.about-values {
  background: var(--light-color);
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.value-card {
  background: white;
  padding: 2rem;
  border-radius: 16px;
  text-align: center;
  box-shadow: var(--shadow);
}

.value-icon {
  font-size: 3rem;
  display: block;
  margin-bottom: 1rem;
}

.value-card h3 {
  color: var(--dark-color);
  margin-bottom: 0.5rem;
}

.value-card p {
  color: var(--text-light);
}

.about-cta {
  background: var(--dark-color);
  color: white;
  text-align: center;
}

.about-cta h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.about-cta p {
  font-size: 1.1rem;
  opacity: 0.8;
  margin-bottom: 2rem;
}

@media (max-width: 768px) {
  .about-hero h1 {
    font-size: 2rem;
  }

  .mission-content {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .mission-icon span {
    font-size: 5rem;
  }
}
</style>
