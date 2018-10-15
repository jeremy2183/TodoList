<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- 組件使用 -->
    <!-- <HeaderView msg="父組件傳遞到子組件"></HeaderView> -->
    <HeaderView :msg="title"></HeaderView>

    <!-- 組件使用 -->
    <ListView></ListView>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
//導入組件
import ListView from './components/List'
import HeaderView from './components/Header'

//App.vue是父組件，ListView是子組件  組件間通信

export default {
  name: 'App',
  components: { //註冊組件
      ListView,HeaderView
  },
  data(){
    return{
      title: "Vue入門學習"
    }
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
