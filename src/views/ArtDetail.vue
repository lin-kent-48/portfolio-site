<template>
  <div class="art-gallery">
    <!-- 回上頁按鈕 -->
    <router-link to="/projects" class="back-link">← 回上頁</router-link>
    
    <h2>2D 繪圖作品集</h2>
    <div class="grid">
      <img src="@/assets/art/2d1.jpg" alt="2D 作品1" />
      <img src="@/assets/art/2d2.jpg" alt="2D 作品2" />
      <img src="@/assets/art/2d3.jpg" alt="2D 作品3" />
      <img src="@/assets/art/2d4.jpg" alt="2D 作品4" />
      <img src="@/assets/art/2d5.jpg" alt="2D 作品5" />
    </div>
  </div>
</template>

<style scoped>
.art-gallery {
  text-align: center;
  /* ✅ 整體置中 */
  padding: 40px 20px;
}

.grid {
  display: flex;
  /* 改用 flexbox */
  justify-content: center;
  /* ✅ 水平置中 */
  flex-wrap: wrap;
  /* ✅ 多張圖片換行 */
  gap: 20px;
  /* 圖片間距 */
}

.grid img {
  width: 300px;   
  border-radius: 8px;
  object-fit: cover;
}
</style>
