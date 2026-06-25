<template>
  <div class="art-gallery">
    <!-- 回上頁按鈕 -->
    <router-link to="/projects" class="back-link">← 回上頁</router-link>

    <h2>3D 建模作品集</h2>
    <div class="grid">
      <img src="@/assets/art/3d1.jpg" alt="3D 作品1" />
      <img src="@/assets/art/3d2.jpg" alt="3D 作品2" />
      <img src="@/assets/art/3d3.jpg" alt="3D 作品3" />
      <img src="@/assets/art/3d4.jpg" alt="3D 作品4" />
      <img src="@/assets/art/3d5.jpg" alt="3D 作品5" />
      <img src="@/assets/art/3d6.png" alt="3D 作品6" />
    </div>
  </div>
</template>

<style scoped>
.art-gallery {
  text-align: center;
  padding: 40px 20px;
}
.grid {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}
.grid img {
  width: 300px; /* ✅ 放大 1.5 倍 */
  border-radius: 8px;
  object-fit: cover;
}
.back-link {
  display: inline-block;
  margin-bottom: 20px;
  color: #3498db;
  text-decoration: none;
  font-weight: bold;
}
.back-link:hover {
  text-decoration: underline;
}
</style>