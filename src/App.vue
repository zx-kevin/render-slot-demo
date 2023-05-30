<template>
  <div class="app-container">
    <el-table :data="dataList">
      <el-table-column label="test1" prop="test"></el-table-column>
      <Column label="test2">
        <template #default="scope">
          <el-button type="primary" link @click="test(scope)">button</el-button>
        </template>
      </Column>
    </el-table>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import Column from './components/column.vue'

const dataList = ref([
  {
    test: 1
  }
])

function test(scope) {
  console.log('scope', scope)
}
</script>

<style lang="scss" scoped></style>
