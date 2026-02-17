<template>
  <nav class="nav">
    <el-row>
      <el-col :span="12" class="logo-container">
        <img src="../assets/logo.png" class="logo" alt="logo" />
        <span class="title">個人整理</span>
      </el-col>
      <el-col :span="12">
        <AuthDropdown />
      </el-col>
    </el-row>
  </nav>
</template>

<script setup lang="ts">
import router from "../router";
import { ref, onMounted, onBeforeUnmount } from 'vue'

const isCollapse = ref(false)
const asideWidth = ref('180px')
const handleResize = () => {
  isCollapse.value = window.innerWidth < 768;
  asideWidth.value = window.innerWidth < 768  ? '64px' : '180px'
}

onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>
.nav {
  position: fixed;
  width: 100%;
  height: 60px;
  background: url("../assets/bar-bg.png");
  color: #BACBD9;
  border-bottom: 1px solid #3B4E59;
  z-index: 1000;
}

.logo-container {
  line-height: 60px;
}

.logo {
  height: 50px;
  width: 50px;
  margin-right: 5px;
  vertical-align: middle;
  display: inline-block;
}

.title {
  vertical-align: middle;
  font-size: 22px;
  font-family: "Microsoft YaHei";
  letter-spacing: 3px;
}
</style>