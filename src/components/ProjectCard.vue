<template>
  <div class="project-card">
    <img :src="image" alt="作品圖片" class="card-img" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <button @click="$emit('view-detail', id)">查看作品</button>
  </div>
</template>

<script setup>
// ⚠️ 不要再 import defineProps
// import { defineProps } from 'vue'

const props = defineProps({
  id: { type: String, required: true },
  title: { type: String, required: true },
  description: { type: String, required: true },
  image: { type: String, required: true }
})
</script>

<style scoped>
.project-card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  width: 250px;
  text-align: center;
}
.card-img {
  width: 100%;
  border-radius: 6px;
  margin-bottom: 8px;
}
button {
  background: #3498db;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 6px;
  cursor: pointer;
}
button:hover {
  background: #2980b9;
}
</style>
