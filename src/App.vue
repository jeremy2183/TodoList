<template>
  <div id="app">
    <img src="./assets/logo.png">

    <!-- 組件使用 -->
    <ListView></ListView>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
//導入組件
import ListView from './components/List'

export default {
  name: 'App',
  components: { //註冊組件
      ListView
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
