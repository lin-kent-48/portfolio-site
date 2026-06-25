<template>
  <nav class="navbar">
    <div class="nav-left">
      <h1>個人作品集</h1>
    </div>
    <div class="nav-right">
      <router-link to="/">首頁</router-link>
      <router-link to="/skills">技能</router-link>
      <router-link to="/projects">作品</router-link>
    </div>
  </nav>
</template>

<script setup>
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #3498db;
  padding: 12px 24px;
  color: white;
}

.nav-left h1 {
  margin: 0;
  font-size: 18px;
}

.nav-right {
  display: flex;
  gap: 20px;
}

.nav-right a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.nav-right a:hover {
  text-decoration: underline;
}
</style>
