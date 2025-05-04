<template>
  <!-- 侧边栏 -->
  <el-row class="menu-container">
    <el-col :span="12">
      <el-menu active-text-color="#ffd04b" background-color="#3B4E59" class="el-menu-vertical" default-active="1"
        text-color="#BACBD9">
        <router-link to="/MyResume">
          <el-menu-item index="1">
            <el-icon>
              <HomeFilled />
            </el-icon>
            <span>首页</span>
          </el-menu-item>
        </router-link>
        <template v-for="menu in menus" :key="menu.path">
          <el-sub-menu v-if="menu.children" :index="menu.path">
            <template #title>
              <el-icon>
                <component :is="menu.icon"></component>
              </el-icon>
              <span>{{ menu.name }}</span>
            </template>
            <el-menu-item-group>
              <router-link v-for="(item, index) in menu.children" :key="index" :to="item.path">
                <el-menu-item :index="item.path">{{ item.name }} </el-menu-item>
              </router-link>
            </el-menu-item-group>
          </el-sub-menu>
        </template>
        <router-link to="/MyResume/userinfo">
          <el-menu-item index="2">
            <el-icon>
              <InfoFilled />
            </el-icon>
            <span>個人資訊</span>
          </el-menu-item>
        </router-link>
        
      </el-menu>
    </el-col>
  </el-row>
</template>

<script setup lang="ts">
import { ref } from "vue";

const menus = ref([
  {
    icon: "Menu",
    name: "作品集",
    path: "SideProject",
    children: [{ path: "/", name: "測試" }],
    // children: [{ path: "fundList", name: "资金流水" }],
  },
  // {
  //   icon: "InfoFilled",
  //   name: "個人資訊",
  //   path: "info",
  //   children: [{ path: "/MyResume/userinfo", name: "履歷" }],
  // },
]);
</script>

<style scoped>
.menu-container {
  position: fixed;
  top: 60px;
  left: 0;
  min-height: 100%;
  
  background-color: #3B4E59;
  z-index: 99;
}

.el-menu {
  border: none;
  background: url("../assets/bar-bg.png");
}

.fa-margin {
  margin-right: 5px;
}

.el-menu-vertical:not(.el-menu--collapse) {
  width: 180px;
  min-height: 100vh;
}

.el-menu-vertical {
  width: 35px;
}

.el-sub-menu .el-menu-item {
  min-width: 180px;
  padding-left: 48px !important;
}

.hiddenDropdown,
.hiddenDropname {
  display: none;
}

a {
  text-decoration: none;
}
</style>