<template>
  <div class="api-test">
    <h2>API 連線測試</h2>
    <button @click="testApi">測試連線</button>
    <div v-if="result">
      <p>結果：{{ result }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const result = ref('')

const testApi = async () => {
  try {
    // 替換為你的 API URL
    const res = await fetch('https://your-api-host.com/test')
    if (!res.ok) throw new Error('連線失敗')
    const data = await res.text()
    result.value = data
  } catch (e: any) {
    result.value = e.message
  }
}
</script>

<style scoped>
.api-test {
  padding: 2rem;
}
</style>
