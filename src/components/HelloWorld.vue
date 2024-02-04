<script setup>
// 注册提交事件
const emit = defineEmits('submitBtn')
import { ref } from 'vue'
const count = ref(0)
// 组件需要先声明是否支持参数传递
const props = defineProps({
  // msg: {
  //   type: String,
  //   required: true
  // }
  title: String,
  value: Number,
  obj: {
    type: Object,
  }
})

// 实现提交事件
function submitBtn(){
  count.value++
  console.log(count.value)
  emit('submitBtn', count.value)
}

console.log(props)
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ "收到了父组件的传参 = " + props.title + "&" + props.value }}</h1>
    <!-- <button @click="$emit('submitBtn', count)"> {{ count }} </button> -->
    <el-row class="mb-4">
    <el-button>Default</el-button>
    <el-button type="primary">Primary</el-button>
    <el-button type="success">Success</el-button>
    <el-button type="info">Info</el-button>
    <el-button type="warning">Warning</el-button>
    <el-button type="danger">Danger</el-button>
  </el-row>
    <el-button type="primary" @click="submitBtn()"> {{ count }} </el-button>
    <el-button type="success">Success</el-button>
    <h3>
      This is a Web to Test Vue3 funcation
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">props.title</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
