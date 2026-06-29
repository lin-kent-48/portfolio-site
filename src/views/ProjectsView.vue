<template>
  <div class="projects-page">
    <h2>我的作品</h2>
    <div class="projects-container">
      <ProjectCard v-for="project in projects" :key="project.id" :id="project.id" :title="project.title"
        :description="project.description" :image="project.image" @view-detail="goDetail" />
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
import ArtPortfolio2D from '@/assets/photoshop.png'
import Art3DCover from '@/assets/3dsmax.png'
import TeamProjectCover from '@/assets/teamproject.png'



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
  },
  {
    id: 'art',
    title: '繪畫作品集',
    description: '2D 繪畫作品展示',
    image: ArtPortfolio2D
  },
  {
    id: 'art3d',
    title: '3D 繪圖作品集',
    description: '展示 3D 建模與渲染作品',
    image: Art3DCover
  },
   {
    id: 'team',
    title: '團體專題作品',
    description: '這是一個團隊合作完成的專題網站，展示了協作與整合能力。',
    image: TeamProjectCover
  }
]

const goDetail = (id) => {
  router.push(`/projects/${id}`)
}
</script>

<style scoped>
.projects-page {
  padding-top: 40px;
  /* 與上方 navbar 保持距離 */
  text-align: center;
  /* 標題置中 */
}

.projects-container {
  display: flex;
  justify-content: center;
  /* ✅ 水平置中 */
  flex-wrap: wrap;
  /* ✅ 多卡片換行 */
  gap: 20px;
  /* 卡片間距 */
  margin-top: 20px;
  /* 與標題保持距離 */
  width: 100%;
  /* 確保容器佔滿寬度 */
}

/* 響應式：手機版直排 */
@media (max-width: 768px) {
  .projects-container {
    flex-direction: column;
    /* 改成直排 */
    align-items: center;
    /* 置中 */
  }
}
</style>
