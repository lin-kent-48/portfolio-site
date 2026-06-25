<template>
  <div class="projects-page">
    <h2>我的作品</h2>
    <div class="projects-container">
      <ProjectCard 
        v-for="project in projects" 
        :key="project.id" 
        :id="project.id" 
        :title="project.title"
        :description="project.description" 
        :image="project.image" 
        @view-detail="goDetail" 
      />
    </div>
  </div>
</template>


<script setup>
import ProjectCard from '@/components/ProjectCard.vue'
import { useRouter } from 'vue-router'

// 匯入圖片
import CityTravelImg from '@/assets/CityTravel.png'
import WorldMartia from '@/assets/WorldMartia.png'
import rockpaper from '@/assets/rockpaper.png'
import ColorDifferenceGame from '@/assets/ColorDifferenceGame.png'

const router = useRouter()

const projects = [
  {
    id: 'travel',
    title: '旅遊網站',
    description: '使用 Vue 打造旅遊介紹網站',
    image: CityTravelImg
  },
  {
    id: 'martial',
    title: '世界武術收藏展示館',
    description: '展示各國武術收藏與互動功能',
    image: WorldMartia
  },
  {
    id: 'rps',
    title: '猜拳 APP',
    description: '互動式剪刀石頭布遊戲',
    image: rockpaper
  },
  {
    id: 'color',
    title: '色彩差異遊戲',
    description: '測試玩家對色彩差異辨識能力的遊戲',
    image: ColorDifferenceGame
  }
]

const goDetail = (id) => {
  router.push(`/projects/${id}`)
}
</script>

<style scoped>
.projects-page {
  padding-top: 40px; /* 與上方 navbar 保持距離 */
  text-align: center; /* 標題置中 */
}

.projects-container {
  display: flex;
  justify-content: center;   /* ✅ 水平置中 */
  flex-wrap: wrap;           /* ✅ 多卡片換行 */
  gap: 20px;                 /* 卡片間距 */
  margin-top: 20px;          /* 與標題保持距離 */
  width: 100%;               /* 確保容器佔滿寬度 */
}

/* 響應式：手機版直排 */
@media (max-width: 768px) {
  .projects-container {
    flex-direction: column;  /* 改成直排 */
    align-items: center;     /* 置中 */
  }
}
</style>

