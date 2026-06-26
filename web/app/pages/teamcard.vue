<script setup lang="ts">
const siteUrl = 'https://codeworldbagel.com'
const pageUrl = `${siteUrl}/teamcard`
const appUrl = 'https://teamcard.codeworldbagel.com'

useSeoMeta({
  title: '團卡 TeamCard - 扣握貝果',
  description: '輕量化的 AI 團隊任務管理平台。看板式專案、工作區分層、即時協作，再加上 AI 協助建立任務，讓團隊把心力放在工作本身，而不是工具設定。',
  ogTitle: '團卡 TeamCard - 扣握貝果',
  ogDescription: '輕量化的 AI 團隊任務管理平台。看板式專案、工作區分層、即時協作，再加上 AI 協助建立任務，讓團隊把心力放在工作本身，而不是工具設定。',
  ogImage: `${siteUrl}/images/teamcard/screenshot-1.jpg`,
  ogUrl: pageUrl,
  ogType: 'website',
  twitterCard: 'summary_large_image',
})

useHead({
  link: [{ rel: 'canonical', href: pageUrl }],
  script: [
    {
      type: 'application/ld+json',
      innerHTML: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'SoftwareApplication',
        name: '團卡 TeamCard',
        description: '輕量化的 AI 團隊任務管理平台。看板式專案、工作區分層、即時協作，再加上 AI 協助建立任務，讓團隊把心力放在工作本身，而不是工具設定。',
        url: pageUrl,
        applicationCategory: 'BusinessApplication',
        operatingSystem: 'Web',
        offers: {
          '@type': 'Offer',
          price: '0',
          priceCurrency: 'TWD'
        },
        author: {
          '@type': 'Organization',
          name: '扣握貝果 CodeWorldBagel'
        }
      })
    }
  ]
})

const showcases = [
  {
    src: '/images/teamcard/screenshot-1.jpg',
    title: '拖拉式看板，狀態一目了然',
    description: '四欄式看板（待處理 / 進行中 / 審核中 / 已完成），拖曳卡片即更新狀態。每張卡片標示優先級、負責人與截止日，整個專案的進度即時可見。'
  },
  {
    src: '/images/teamcard/screenshot-2.jpg',
    title: '工作區分層，專案與成員集中管理',
    description: '工作區 × 專案的清楚兩層結構，搭配角色權限。一頁掌握所有專案進度、團隊成員與本期 AI 點數用量。'
  },
  {
    src: '/images/teamcard/screenshot-3.jpg',
    title: '我的任務，今天該做什麼一眼掌握',
    description: '自動彙整今日到期、逾期、進行中與本週到期的任務，跨專案集中在同一頁。每天打開就知道從哪裡開始。'
  }
]

const features = [
  {
    icon: 'kanban',
    title: '拖拉式看板',
    description: '四欄看板拖曳即更新狀態，待處理到完成一目了然，專案進度即時同步'
  },
  {
    icon: 'ai',
    title: 'AI 協助建立任務',
    description: '用一句話描述需求，AI 自動草擬任務標題、描述、建議負責人與截止日'
  },
  {
    icon: 'layers',
    title: '工作區分層',
    description: '工作區 × 專案兩層結構，角色權限清楚，團隊與專案集中管理不混亂'
  },
  {
    icon: 'bell',
    title: '即時協作通知',
    description: '指派成員、留言討論、活動紀錄，被指派或被提及立即在通知中心提醒'
  }
]
</script>

<template>
  <div class="teamcard-page">
    <!-- Hero -->
    <section class="tc-hero">
      <div class="tc-hero-bg"></div>
      <div class="container">
        <div class="tc-hero-content">
          <div class="tc-hero-badge">AI × 團隊任務管理</div>
          <div class="tc-hero-icon">
            <img src="/images/teamcard/icon.png" alt="團卡 TeamCard" />
          </div>
          <h1 class="tc-hero-title">團卡</h1>
          <p class="tc-hero-subtitle">TeamCard</p>
          <p class="tc-hero-tagline">比 Notion 更有結構，比 Asana 更簡單，<br>讓團隊把心力放在工作本身，而不是工具設定。</p>
          <div class="tc-hero-actions">
            <a
              :href="appUrl"
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-primary tc-hero-btn"
            >
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M15 3h6v6"/>
                <path d="M10 14L21 3"/>
                <path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/>
              </svg>
              免費開始
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Features -->
    <section class="tc-features">
      <div class="container">
        <h2 class="tc-section-title">核心功能</h2>
        <p class="tc-section-subtitle">看板式專案、工作區分層、即時協作，再加上 AI 協助建立任務</p>
        <div class="tc-features-grid">
          <div v-for="feature in features" :key="feature.title" class="tc-feature-card">
            <div class="tc-feature-icon">
              <!-- Kanban -->
              <svg v-if="feature.icon === 'kanban'" width="28" height="28" viewBox="0 0 28 28" fill="none">
                <rect x="4" y="5" width="5.5" height="18" rx="1.5" stroke="currentColor" stroke-width="1.8"/>
                <rect x="11.25" y="5" width="5.5" height="12" rx="1.5" stroke="currentColor" stroke-width="1.8"/>
                <rect x="18.5" y="5" width="5.5" height="15" rx="1.5" stroke="currentColor" stroke-width="1.8"/>
              </svg>
              <!-- AI sparkle -->
              <svg v-if="feature.icon === 'ai'" width="28" height="28" viewBox="0 0 28 28" fill="none">
                <path d="M14 4l1.9 4.9L20.8 10.8 15.9 12.7 14 17.6 12.1 12.7 7.2 10.8 12.1 8.9 14 4z" stroke="currentColor" stroke-width="1.8" stroke-linejoin="round"/>
                <path d="M21 16.5l.7 1.9 1.9.7-1.9.7-.7 1.9-.7-1.9-1.9-.7 1.9-.7.7-1.9z" fill="currentColor"/>
              </svg>
              <!-- Layers -->
              <svg v-if="feature.icon === 'layers'" width="28" height="28" viewBox="0 0 28 28" fill="none">
                <path d="M14 4l9 5-9 5-9-5 9-5z" stroke="currentColor" stroke-width="1.8" stroke-linejoin="round"/>
                <path d="M5 14l9 5 9-5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M5 19l9 5 9-5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
              <!-- Bell -->
              <svg v-if="feature.icon === 'bell'" width="28" height="28" viewBox="0 0 28 28" fill="none">
                <path d="M14 4c-3 0-5.5 2.4-5.5 5.4 0 5-2 6.6-2 6.6h15s-2-1.6-2-6.6C19.5 6.4 17 4 14 4z" stroke="currentColor" stroke-width="1.8" stroke-linejoin="round"/>
                <path d="M12 20a2 2 0 004 0" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
              </svg>
            </div>
            <h3 class="tc-feature-title">{{ feature.title }}</h3>
            <p class="tc-feature-desc">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Showcase -->
    <section class="tc-showcase">
      <div class="container">
        <h2 class="tc-section-title">產品預覽</h2>
        <p class="tc-section-subtitle">從看板、工作區到我的任務的完整體驗</p>
        <div
          v-for="(item, index) in showcases"
          :key="item.src"
          class="tc-showcase-item"
          :class="{ 'tc-showcase-reverse': index % 2 !== 0 }"
        >
          <div class="tc-showcase-image">
            <img :src="item.src" :alt="item.title" />
          </div>
          <div class="tc-showcase-text">
            <h3 class="tc-showcase-title">{{ item.title }}</h3>
            <p class="tc-showcase-desc">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="tc-cta">
      <div class="container">
        <div class="tc-cta-inner">
          <h2 class="tc-cta-title">立即組建你的團隊看板</h2>
          <p class="tc-cta-desc">使用 Google 登入，30 秒建立帳號、不需信用卡，<br>免費開始，今天就讓 AI 幫你把任務排好。</p>
          <a
            :href="appUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-primary tc-cta-btn"
          >
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M15 3h6v6"/>
              <path d="M10 14L21 3"/>
              <path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/>
            </svg>
            前往 teamcard.codeworldbagel.com
          </a>
        </div>
      </div>
    </section>

    <ContactSection default-product="teamcard" />
  </div>
</template>

<style scoped>
.teamcard-page {
  --tc-accent: #1e4f82;
  --tc-accent-dark: #15375a;
  --tc-accent-light: #e9eef7;
}

/* Hero */
.tc-hero {
  position: relative;
  min-height: 100dvh;
  display: flex;
  align-items: center;
  padding: 100px 0 80px;
  overflow: hidden;
}

.tc-hero .container {
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: center;
}

.tc-hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse at 20% 50%, rgba(30, 79, 130, 0.1) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 20%, rgba(30, 79, 130, 0.05) 0%, transparent 50%);
  pointer-events: none;
}

.tc-hero-content {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 560px;
}

.tc-hero-badge {
  display: inline-block;
  padding: 6px 14px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--tc-accent-dark);
  background-color: var(--tc-accent-light);
  border-radius: 20px;
  margin-bottom: 24px;
}

.tc-hero-icon {
  margin-bottom: 24px;
}

.tc-hero-icon img {
  width: 80px;
  height: 80px;
  border-radius: 18px;
  box-shadow: 0 8px 32px rgba(30, 79, 130, 0.25);
}

.tc-hero-title {
  font-size: 52px;
  font-weight: 700;
  color: var(--color-text);
  letter-spacing: -0.02em;
  line-height: 1.1;
  margin-bottom: 8px;
}

.tc-hero-subtitle {
  font-size: 20px;
  font-weight: 500;
  color: var(--tc-accent-dark);
  margin-bottom: 20px;
}

.tc-hero-tagline {
  font-size: 17px;
  color: var(--color-text-light);
  line-height: 1.7;
  margin-bottom: 36px;
}

.tc-hero-actions {
  display: flex;
  justify-content: center;
  gap: 16px;
}

.tc-hero-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  font-size: 16px;
  border-radius: 10px;
  background-color: var(--tc-accent);
  color: white;
  border: none;
  text-decoration: none;
  transition: var(--transition);
}

.tc-hero-btn:hover {
  background-color: var(--tc-accent-dark);
  transform: translateY(-2px);
}

/* Showcase */
.tc-showcase {
  padding: 80px 0;
}

.tc-showcase-item {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
  padding: 40px 0;
}

.tc-showcase-item + .tc-showcase-item {
  border-top: 1px solid var(--color-border);
}

.tc-showcase-reverse {
  direction: rtl;
}

.tc-showcase-reverse > * {
  direction: ltr;
}

.tc-showcase-image {
  display: flex;
  justify-content: center;
}

.tc-showcase-image img {
  width: 100%;
  max-width: 100%;
  border-radius: 12px;
  box-shadow: 0 16px 48px rgba(0, 0, 0, 0.12);
  border: 1px solid var(--color-border);
}

.tc-showcase-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.tc-showcase-title {
  font-size: 26px;
  font-weight: 700;
  color: var(--color-text);
  margin-bottom: 12px;
  letter-spacing: -0.01em;
}

.tc-showcase-desc {
  font-size: 16px;
  color: var(--color-text-light);
  line-height: 1.7;
}

/* Section titles */
.tc-section-title {
  font-size: 32px;
  font-weight: 700;
  color: var(--color-text);
  text-align: center;
  margin-bottom: 8px;
  letter-spacing: -0.01em;
}

.tc-section-subtitle {
  font-size: 16px;
  color: var(--color-text-light);
  text-align: center;
  margin-bottom: 48px;
}

/* Features */
.tc-features {
  padding: 80px 0;
  background-color: var(--color-background-alt);
}

.tc-features-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
}

.tc-feature-card {
  background: var(--color-background);
  border: 1px solid var(--color-border);
  border-radius: 14px;
  padding: 28px 24px;
  text-align: center;
  transition: var(--transition);
}

.tc-feature-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.06);
  border-color: var(--tc-accent-light);
}

.tc-feature-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 56px;
  height: 56px;
  border-radius: 14px;
  background: var(--tc-accent-light);
  color: var(--tc-accent-dark);
  margin-bottom: 16px;
}

.tc-feature-title {
  font-size: 17px;
  font-weight: 600;
  color: var(--color-text);
  margin-bottom: 8px;
}

.tc-feature-desc {
  font-size: 14px;
  color: var(--color-text-light);
  line-height: 1.6;
}

/* CTA */
.tc-cta {
  padding: 80px 0;
}

.tc-cta-inner {
  text-align: center;
  max-width: 520px;
  margin: 0 auto;
}

.tc-cta-title {
  font-size: 28px;
  font-weight: 700;
  color: var(--color-text);
  margin-bottom: 12px;
}

.tc-cta-desc {
  font-size: 16px;
  color: var(--color-text-light);
  margin-bottom: 28px;
  line-height: 1.6;
}

.tc-cta-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 32px;
  font-size: 16px;
  border-radius: 10px;
  background-color: var(--tc-accent);
  color: white;
  border: none;
  text-decoration: none;
  transition: var(--transition);
}

.tc-cta-btn:hover {
  background-color: var(--tc-accent-dark);
  transform: translateY(-2px);
}

/* Responsive */
@media (max-width: 1024px) {
  .tc-features-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .tc-showcase-item {
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .tc-hero {
    min-height: auto;
    padding: 40px 0;
  }

  .tc-hero-content {
    min-height: calc(100dvh - 60px - 80px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .tc-hero-title {
    font-size: 36px;
  }

  .tc-hero-tagline br {
    display: none;
  }

  .tc-showcase {
    padding: 60px 0;
  }

  .tc-showcase-item {
    grid-template-columns: 1fr;
    gap: 24px;
    text-align: center;
  }

  .tc-showcase-reverse {
    direction: ltr;
  }

  .tc-showcase-title {
    font-size: 22px;
  }

  .tc-features {
    padding: 60px 0;
  }

  .tc-features-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .tc-section-title {
    font-size: 26px;
  }

  .tc-cta {
    padding: 60px 0;
  }

  .tc-cta-desc br {
    display: none;
  }
}
</style>
