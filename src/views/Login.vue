<template>
  <div class="login">
    <section class="form-container">
      <div class="manage-tip">
        <span class="title">Login Page</span>
        <el-form
          :rules="rules"
          ref="ruleFormRef"
          :model="loginUser"
          class="loginForm"
          label-width="80px"
        >
          <el-form-item label="email" prop="email">
            <el-input
              v-model="loginUser.email"
              placeholder="email"
            ></el-input>
          </el-form-item>
          <el-form-item label="password" prop="password">
            <el-input
              v-model="loginUser.password"
              placeholder="password"
              type="password"
            ></el-input>
          </el-form-item>

          <el-form-item>
            <el-button @click="handleSubmit(ruleFormRef)" class="submit-btn"
              >login</el-button
            >
          </el-form-item>

          <div class="tiparea">
            <p>
              <router-link to="/register">regist</router-link> now
            </p>
          </div>
        </el-form>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from "vue";
import { registerType, registerRulesType, userType } from "../utils/types";
import { FormInstance } from "element-plus";
import axios from "../utils/http";
import { useRouter } from "vue-router";
import jwt_decode from "jwt-decode";
import { useAuthStore } from "../store";

const ruleFormRef = ref<FormInstance>();
const router = useRouter();
const store = useAuthStore();

const loginUser = ref<registerType>({
  email: "test@example.com",
  password: "12345678",
});

const rules = reactive<registerRulesType>({
  email: [
    {
      type: "email",
      required: true,
      message: "The email format is incorrect",
      trigger: "blur",
    },
  ],
  password: [
    { required: true, message: "Password cannot be empty", trigger: "blur" },
    { min: 6, max: 30, message: "Password length between 6 and 30 characters", trigger: "blur" },
  ],
});

const handleSubmit = (formEl: FormInstance | undefined) => {
  if (!formEl) return;
  formEl.validate(async (valid: boolean) => {
    if (valid) {
      const {
        data: { success, token },
      } = await axios.post("/api/users/login", loginUser.value);

      if (success && token) {
        localStorage.setItem("token", token);

        // 解析token
        const decode: userType = jwt_decode(token);
        console.log(decode);

        store.setAuth(!!decode);
        store.setUser(decode);

        // @ts-ignore
        ElMessage({
          message: "Login Success.",
          type: "success",
        });

        router.push("/MyResume");
      }
    } else {
      console.log("error submit!");
      return false;
    }
  });
};
</script>

<style scoped>
</style>