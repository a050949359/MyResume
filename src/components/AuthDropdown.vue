<template>
    <div class="user">
        <el-dropdown trigger="click" @command="handleCommand">
            <span class="el-dropdown-link">
                <img v-if="store.user.avatar" :src="store.user.avatar" class="avatar" alt="" />
                <img v-else src="../assets/default.jpg" class="avatar" alt="" />
                <p v-if="!store.getAuthenticated">未登入</p>
                <p v-else>歡迎 {{ store.user.name }}</p>
                <el-icon><arrow-down /></el-icon>
            </span>
            <template #dropdown>
                <el-dropdown-menu v-if="!store.getAuthenticated">
                    <el-dropdown-item command="login">登入</el-dropdown-item>
                    <el-dropdown-item command="register">註冊</el-dropdown-item>
                </el-dropdown-menu>
                <el-dropdown-menu v-else>
                    <el-dropdown-item command="profile">個人資料</el-dropdown-item>
                    <el-dropdown-item command="logout">登出</el-dropdown-item>
                </el-dropdown-menu>
            </template>
        </el-dropdown>
    </div>
</template>

<script setup lang="ts">
import { Ref } from "vue";
import { useAuthStore } from "../store";
import { ElMessage } from 'element-plus'
import router from "../router";

const store: any = useAuthStore();

const handleCommand = (command: string) => {
    switch (command) {
        case 'login':
            // 這裡應接到你的登入邏輯
            store.setAuth(true);
            ElMessage.success('已登入');
            router.push("/MyResume/login");
            break
        case 'register':
            // 這裡應接到你的登入邏輯
            store.setAuth(true);
            // ElMessage.success('已註冊');
            router.push("/MyResume/register");
            break
        case 'logout':
            localStorage.removeItem("token");

            store.setAuth(false);
            store.setUser(null);

            router.push("/MyResume");
            break
        case 'profile':
            router.push("/MyResume/userinfo");

    }
}
</script>

<style scoped>
.user {
    /* line-height: 60px; */
    text-align: right;
    align-items: center;  
    padding-right: 10px;
}

.el-dropdown {
    height: 100%;
}

.el-dropdown-link {
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 4px;
}

.avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    vertical-align: middle;
    display: inline-block;
    margin-top: 10px;
    margin-bottom: 10px;
}

.welcome-content {
    display: inline-block;
    width: auto;
    vertical-align: middle;
    padding: 0 5px;
}

.content {
    line-height: 20px;
    text-align: center;
    font-size: 14px;
}

.welcome {
    font-size: 12px;
}

.username {
    color: #409eff;
    font-weight: bolder;
}

.dropdown {
    cursor: pointer;
    margin-right: 5px;
}

.el-dropdown {
    color: #fff;
}

.dropdown i {
    margin-top: 20px;
}
</style>