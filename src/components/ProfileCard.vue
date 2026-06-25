<template>
  <div class="card">
    <!-- 左側文字資訊 -->
    <div class="card-info">
      <p><strong>姓名：</strong>{{ name }}</p>
      <p><strong>稱呼：</strong>{{ title }}</p>

      <!-- 了解更多按鈕 -->
      <button class="more-btn" @click="toggleBio">
        {{ showBio ? '收合' : '了解更多' }}
      </button>

      <!-- 展開自傳文字 -->
      <transition name="fade">
        <div v-if="showBio" class="bio">
          <p>
            我是有25年跨行業域歷經驗的工作者，目前在學習前端網頁設計，
            熟悉 Vue3、JavaScript，喜歡設計互動式 UI 元件，
            並持續學習新技術來提升作品品質。
            在學習過程中，我注重程式碼結構化與互動設計，
            期望能打造出兼具美感與功能性的前端作品。
          </p>
        </div>
      </transition>
    </div>

    <!-- 右側頭像 -->
    <img :src="avatarImg" alt="頭像" class="avatar" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
// import { defineProps } from 'vue'
import avatarImg from '@/assets/avater-new.jpeg'

const props = defineProps({
  name: { type: String, required: true },
  title: { type: String, required: true },
  resumeUrl: { type: String, required: false }
})

const showBio = ref(false)
const toggleBio = () => {
  showBio.value = !showBio.value
}
</script>

<style scoped>
.card {
  display: flex;
  align-items: flex-start; /* 左右頂端對齊 */
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 16px;
  width: 350px;
  background-color: #f9f9f9;
  gap: 16px;
}

.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #3498db;
  align-self: flex-start; /* 固定在頂端 */
}

.card-info {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.more-btn {
  background-color: #3498db;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.more-btn:hover {
  background-color: #2980b9;
}

.bio {
  margin-top: 12px;
  background: #f9f9f9;
  padding: 10px;
  border-radius: 6px;
  line-height: 1.6;
}

/* 淡入淡出動畫 */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
