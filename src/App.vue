<script setup>
import Sidenav from './components/Sidenav.vue'
import AdminSideNav from "@/components/AdminSideNav.vue";
import { useRoute } from 'vue-router';

const route = useRoute();
</script>

<template>
  <div id="app" class="app-container">
    <Sidenav v-if="route.name !== 'Login' && route.name !== 'AdminManage' && route.name !== 'AdminCourse' && route.name !== 'AdminLab' && route.name !== 'AdminLabManager'" />
    <AdminSideNav v-if="route.name ==='AdminManage'|| route.name === 'AdminCourse' || route.name === 'AdminLab' || route.name === 'AdminLabManager'"/>
    <div class="main-content">
      <router-view />
    </div>
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  height: 100vh; /* 使得页面填充整个视口高度 */
}

.main-content {
  flex-grow: 1; /* 使主内容区占据剩余的空间 */
  background-color: #f7f7f7; /* 可自定义背景颜色 */
  overflow-y: auto; /* 禁用滚动条 */
}
</style>
