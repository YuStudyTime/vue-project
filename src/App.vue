<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

function callback(n) {
  console.log("App" + n)
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">    
      <!-- // 这里是父组件往子组件中传递数据 -->
      <!-- // 这里测试几种组件参数传递方式 -->
      <!-- // 1. 之间传递 msg String类型 -->
      <!-- <HelloWorld msg="Vue3 Funcation Test Project!" /> -->
      <!-- // 2. 传递对象 obj 对象类型 注意这里的：号  错误的写法会导致传递过去的数据是字符串-->
      <HelloWorld @submitBtn="callback" title="WenPei big SB!" :value="123" :obj="{title: 'WenPei', value: 0}" />
  
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/test">Test</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
