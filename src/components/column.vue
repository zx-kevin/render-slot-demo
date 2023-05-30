<template>
  <el-table-column v-bind="$attrs">
    <template #default="scope">
      <slot v-bind="scope"></slot>

      <renderComponent></renderComponent>
    </template>
  </el-table-column>
</template>

<script>
export default {
  name: 'TTableColumn'
}
</script>

<script setup>
import { ElTableColumn } from 'element-plus'
import { useSlots, h, defineComponent, onMounted } from 'vue'

const slots = useSlots()

const renderComponent = defineComponent({
  setup(props, { attrs }) {
    return () =>
      h(
        'div',
        slots.default().map((com) => com)
      )
  }
})

onMounted(() => {
  console.log('1')
})
</script>

<style lang="scss" scoped></style>
