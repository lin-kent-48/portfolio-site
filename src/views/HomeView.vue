<template>
  <div class="home">
    <!-- Hero 區塊 -->
    <section class="hero">
      <!-- 左邊 ProfileCard -->
      <ProfileCard
        name="林建宏"
        title="前端工程師學習者"
        resumeUrl="https://example.com/resume"
      />

      <!-- 右邊 Hero 插圖 -->
      <div class="hero-image">
        <img src="@/assets/illustrations/hero-illustration-bluegreen.png" alt="Hero 插圖" />
      </div>
    </section>
  </div>
</template>

<script setup>
import ProfileCard from '@/components/ProfileCard.vue'
</script>

<style scoped>
.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px;
  padding: 60px 20px;
  background: linear-gradient(120deg, #a8edea, #ecf9f6);
}

/* 桌面版插圖 */
.hero-image img {
  width: 360px;
  max-width: 100%;
  height: auto;
  animation: fadeIn 1.2s ease-in-out;
}

/* 手機版響應式：隱藏插圖 */
@media (max-width: 768px) {
  .hero {
    flex-direction: column;   /* 改成上下排列 */
    text-align: center;
  }

  .hero-image {
    display: none;            /* 手機版隱藏插圖 */
  }
}

/* 動畫效果 */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
