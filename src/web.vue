<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <input type="button" value="获取笑话">
    <p> {{ joke }} </p>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  data(){
      return{
        joke:"这是个笑话"  
      }
      
  },
  methods:{
      getJoke:function(){

    this.$http.get("https://autumnfish.cn/api/joke").then((response) => {
      console.log(response)
    })
      }
  }
};
// 接口：随机获取一条笑话
// 请求地址：https://autumnfish.cn/api/joke
// 请求方法：get
// 请求参数：无
// 相应内容：随机笑话
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>

