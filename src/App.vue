<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- 組件使用 -->
    <!-- <HeaderView msg="父組件傳遞到子組件"></HeaderView> -->
    <HeaderView :msg="title"></HeaderView>

    <!-- 組件使用 -->
    <ListView @myMsg="getData"></ListView>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
//導入組件
import ListView from './components/List'
import HeaderView from './components/Header'

//App.vue是父組件，ListView是子組件  組件間通信
// 父組件 --> 子組件  props選項
// 子組件 --> 父組件  自定義事件

export default {
  name: 'App',
  components: { //註冊組件
      ListView,HeaderView
  },
  data(){
    return{
      title: "Vue入門學習"
    }
  },
  methods: {
    getData(msg){
      console.log("App.vue組件中:" + msg);
      this.title = msg;
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
