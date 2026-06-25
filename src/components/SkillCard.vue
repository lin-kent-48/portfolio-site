<template>
  <div class="skill-card">
    <!-- 技能 icon -->
    <img :src="icon" alt="技能圖示" class="skill-icon" />

    <!-- 技能名稱 -->
    <h3 class="skill-name">{{ name }}</h3>

    <!-- 技能熟練度 (星星) -->
    <div class="stars">
      <span 
        v-for="n in 5" 
        :key="n" 
        class="star" 
        :class="{ active: n <= level }"
      >★</span>
    </div>
  </div>
</template>

<script setup>
// import { defineProps } from 'vue'

const props = defineProps({
  name: { type: String, required: true },   // 技能名稱
  icon: { type: String, required: true },   // 技能 icon 圖片網址
  level: { type: Number, required: true }   // 熟練度 (1~5)
})
</script>

<style scoped>
.skill-card {
  width: 150px;
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  text-align: center;
  background-color: #f9f9f9;
}

.skill-icon {
  width: 50px;
  height: 50px;
  object-fit: contain;
  margin-bottom: 8px;
}

.skill-name {
  font-size: 16px;
  margin: 6px 0;
}

.stars {
  display: flex;
  justify-content: center;
  gap: 4px;
}

.star {
  font-size: 18px;
  color: #ccc;
}

.star.active {
  color: gold;
}
</style>
