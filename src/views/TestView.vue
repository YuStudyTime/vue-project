<template>
  <div class="common-layout">
    <el-container>
      <el-aside width="200px">
        <el-scrollbar max-height="800px">
          <p v-for="item in count" :key="item" class="scrollbar-demo-item">{{ item }}</p>
        </el-scrollbar>
      </el-aside>
      <el-container >
        <el-header class="el-header-demo">
          <el-scrollbar>
            <div class="scrollbar-flex-content">
              <p v-for="item in mRow" :key="item" class="scrollbar-demo-item-h">
                {{ item }}
              </p>
            </div>
          </el-scrollbar>
        </el-header>
        <el-main style="max-width: 100vh">
          <el-scrollbar max-height="800px" >
            <el-table :data="tableData">
              <el-table-column prop="date" label="Date" width="140" />
              <el-table-column prop="name" label="Name" width="120" />
              <el-table-column prop="address" label="Address" />
            </el-table>
          </el-scrollbar>
        </el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const count = ref(100)
const mRow = ref(150)
const item = {
  date: '2016-05-02',
  name: 'Tom',
  address: 'No. 189, Grove St, Los Angeles',
}
const tableData = ref(Array.from({ length: 100 }).fill(item))
</script>

<style>
@media (min-width: 1024px) {
  .test {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
  .el-header-demo {
    background-color: #373d41;
    max-width: 100vh;
    min-height: 70px;
  }
  .scrollbar-demo-item {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
  background: var(--el-color-primary-light-9);
  color: var(--el-color-primary);
}
.scrollbar-demo-item-h {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100px;
  height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
  background: var(--el-color-danger-light-9);
  color: var(--el-color-danger);
}
.scrollbar-flex-content {
  display: flex;
}
}
</style>
