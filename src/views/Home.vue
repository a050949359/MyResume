<template>
  <el-container class="home">
    <Navbar />
    <el-container class="container">
      
      <Sidebar />
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </el-container>
</template>

<script setup lang="ts">
import { onMounted } from "vue";
import axios from "../utils/http";

onMounted(async () => {
  try {
    const data = await axios.get("/api/users/current");
    console.log(data);
  } catch (error) {
    console.log(error);
  }
});
</script>

<style scoped>
.home {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.container {
  padding-top: 60px;
  height: 100%;
}

.container .el-main {
  padding: 0;
}
</style>