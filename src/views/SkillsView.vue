<script setup>
import SkillCard from '@/components/SkillCard.vue'

// 引入本地圖片
import htmlIcon from '@/assets/htmlicon.png'
import cssIcon from '@/assets/cssicon.png'
import jsIcon from '@/assets/jsicon.png'
import vueIcon from '@/assets/vueicon.png'
import photoshop from '@/assets/photoshop.png'
import illustrator from '@/assets/illustrator.png'
import figma from '@/assets/figma.png'
import threeDsMax from '@/assets/3dsmax.png'
import gitIcon from '@/assets/giticon.png'


// 技能清單陣列
const skills = [
  { name: 'HTML', icon: htmlIcon, level: 3 },
  { name: 'CSS', icon: cssIcon, level: 3 },
  { name: 'JavaScript', icon: jsIcon, level: 3 },
  { name: 'Vue.js', icon: vueIcon, level: 3 },
  { name: 'photoshop', icon: photoshop, level: 4 },
  { name: 'illustrator', icon: illustrator, level: 3 },
  { name: 'figma', icon: figma, level: 2 },
  { name: '3dsmax', icon: threeDsMax, level: 4 },
  { name: 'Git', icon: gitIcon, level: 2 },
]
</script>

<template>
  <div class="skills-page">
    <h2>我的技能</h2>
    <div class="skills-container">
      <SkillCard
        v-for="skill in skills"
        :key="skill.name"
        :icon="skill.icon"
        :name="skill.name"
        :level="skill.level"
      />
    </div>
  </div>
</template>

<style scoped>
.skills-page {
  padding-top: 40px; /* 往下移動，避免貼太緊 */
  text-align: center; /* 標題置中 */
}

.skills-container {
  display: flex;
  justify-content: center; /* 卡片置中 */
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 20px;
}

/* 響應式：手機版直排 */
@media (max-width: 768px) {
  .skills-container {
    flex-direction: column; /* 改成直排 */
    align-items: center;    /* 置中 */
  }
}
</style>