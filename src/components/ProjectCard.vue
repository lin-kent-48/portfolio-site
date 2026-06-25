<template>
  <div class="project-card">
    <img :src="image" alt="作品圖片" class="card-img" />
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <div class="card-footer">
      <button @click="$emit('view-detail', id)">查看作品</button>
    </div>
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
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  width: 250px;
  /* 移除 height: 350px */
  text-align: center;
}

.card-img {
  width: 100%;
  border-radius: 6px;
  margin-bottom: 8px;
}

.card-footer {
  margin-top: auto;
  /* ✅ 把按鈕推到底部 */
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
