<template>
  <div class="index">
    <div class="container">
      <h1>ohya 履歷用網頁</h1>
      <h3>開發中</h3>
      <el-table :data="tableData" :cell-style="cellStyle" style="width: 60%">
        <el-table-column prop="list" label="To-Do-List" />
      </el-table>
      
    </div>
  </div>
</template>

<script setup lang="ts">

const tableData = [
  {
    list: "✅github vue 專案使用 github actions 更新 github pages"
  },
  {
    list: "登入功能"
  },
  {
    list: "dashboard 使用隨機資料 chart.js websocket & flask API & indfluxdb V3 core"
  },
  {
    list: "聊天室 flask socket.io redis"
  },
  {
    list: "簡易購物網站 php laravel mysql"
  },
  {
    list: "前幾項的各種後台設定"
  },
]

import type { CSSProperties } from 'vue'
import type { TableColumnCtx } from 'element-plus/es/components/table/src/table-column/defaults'

interface TableRow {
  list: string
}

const cellStyle = (
  { row, column, rowIndex, columnIndex }: {
    row: TableRow
    column: TableColumnCtx<TableRow>
    rowIndex: number
    columnIndex: number
  }
): CSSProperties => {
  return {
    color: '#343A40',
  }
}
</script>

<style scoped>

.index {
  width: 100%;
  height: 100%;
  background: url("../assets/showcase.png") no-repeat;
  background-size: 100% 100%;
}

.container {
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  text-align: center;
  display: flex;
  flex-direction: column;  
  align-items: center;  
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px); /* 👈 關鍵：模糊背景 */
}

body {
  font-family: "Century Gothic", 'Lato', sans-serif;
}

h1 { 
  margin-top: 10%; 
  color: #343A40;
  font-size: 48px;
}

h3 {
  margin-top: 5%;
  color: #343A40;
  font-size: 32px;
}

el-table {
  width: 60%;
}

::v-deep .el-table th,
::v-deep .el-table tr, 
::v-deep .el-table td {
  background-color: transparent !important;
}
::v-deep .el-table td.el-table__cell, .el-table th.el-table__cell.is-leaf {
  border-bottom: 0;
}
::v-deep .el-table--enable-row-transition .el-table__body td.el-table__cell  {
  background-color: transparent !important;
}
::v-deep .el-table td.el-table__cell div.cell  {
  background-color: transparent !important;
}
::v-deep .el-table  {
  background-color: transparent !important;
}
::v-deep .el-table__row  {
  background-color: transparent !important;
}

::v-deep .el-table::before {
    background-color: transparent !important;
}

:deep(.el-table th.el-table__cell.is-leaf) {
  border-bottom: none;
}

:deep(.el-table__inner-wrapper:before) {
  bottom: 0;
  height: 0px;
  left: 0;
}

::v-deep .el-table thead th {
  color: #000 !important;
}

</style>