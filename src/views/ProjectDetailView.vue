<template>
  <div class="project-detail">

    <!-- 返回鍵 -->
    <router-link to="/projects" class="back-link">← 回到作品列表</router-link>


    <!-- 顯示作品標題與內容 -->
    <h2>{{ project.title }}</h2>
    <img :src="project.image" alt="作品圖片" class="detail-img" />
    <p>{{ project.description }}</p>
    <ul>
      <li v-for="tag in project.tags" :key="tag">{{ tag }}</li>
    </ul>
    <div class="links">
      <a :href="project.github" target="_blank">GitHub 連結</a>
    </div>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router'
import CityTravelImg from '@/assets/CityTravel.png'
import WorldMartia from '@/assets/WorldMartia.png'
import rockpaper from '@/assets/rockpaper.png'
import ColorDifferenceGame from '@/assets/ColorDifferenceGame.png'

const route = useRoute()
const id = route.params.id

// 模擬作品資料，可改成 API 或 store
const projectData = {
  travel: {
    title: '旅遊網站',
    description: '這是一個旅遊介紹網站，包含景點、行程規劃與附近美食。',
    image: CityTravelImg,
    tags: ['Vue.js', 'CSS', 'API'],
    github: 'https://lin-kent-48.github.io/city-travel-guide/',
  },
  martial: {
    title: '世界武術收藏展示館',
    description: '這是一個展示世界各國武術收藏的網站，包含新增收藏、統計資訊、收藏列表等互動功能。',
    image: WorldMartia,
    tags: ['Vue.js', 'Pinia', '互動式UI'],
    github: 'https://lin-kent-48.github.io/theme-collection/',
  },
  rps: {
    title: '猜拳 APP',
    description: '這是一個互動式剪刀石頭布遊戲，玩家可以與電腦對戰，並有分數紀錄與清除功能。',
    image: rockpaper,
    tags: ['JavaScript', '互動式UI'],
    github: 'https://lin-kent-48.github.io/ScissorsRockPaper/',
  },
  color: {
    title: '色彩差異遊戲',
    description: '這是一個測試玩家對色彩差異辨識能力的遊戲，包含多種難度等級。',
    image: ColorDifferenceGame,
    tags: ['JavaScript', '互動式UI'],
    github: 'https://lin-kent-48.github.io/ColorDifferenceGame/',
  }
}

const project = projectData[id]
</script>

<style scoped>
.project-detail ul {
  list-style: none;
  /* 移除黑點 */
  padding: 0;
  /* 移除左邊縮排 */
  margin: 0;
  /* 移除額外間距 */
}

.project-detail li {
  display: inline-block;
  /* 橫向排列 */
  margin: 0 8px;
  background: #f0f0f0;
  padding: 4px 10px;
  border-radius: 6px;
}

.project-detail {
  padding: 40px 20px;
  text-align: center;
  /* ✅ 整體置中 */
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

.detail-img {
  width: 100%;
  max-width: 600px;
  /* ✅ 限制最大寬度，避免太寬 */
  border-radius: 8px;
  margin: 20px auto;
  /* ✅ 圖片置中 */
  display: block;
}

.links {
  margin-top: 20px;
}

.links a {
  margin: 0 12px;
  color: #3498db;
  text-decoration: none;
}

.links a:hover {
  text-decoration: underline;
}
</style>
