<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <!-- <ui>
      <li v-for="(item, index) in arr" v-bind:key="item">人名{{ index + 1 }}：{{ item.name }}</li>
    </ui>
    <input type="button" value="增加人名" @click="add" />
    <input type="button" value="删除左边人名" @click="remove" /> -->

    <!-- <input type="button" value="点一下试试看" @click="doIt('hi','你好啊','你是谁')">
    <input type="text" value="请输入账号" @keyup.enter="ok"/>
    <input type="button" value="提交" @click="ok"  /> -->

    <!-- <input type="button" value="修改message" @click="setM">
  <input type="text" v-model="message" @keyup.enter="getM">
  <h2>{{ message }}</h2> -->

    <!-- 我的记事本案例 -->
    <section class="note">
      <header class="header">
        <h1>我的记事本</h1>
        <input
          v-model="inputValue"
          @keyup.enter="add"
          autofocus="autofocus"
          autocomplete="off"
          placeholder="请输入任务"
          class="new_todo"
        />
      </header>
      <section class="main">
        <ul class="todo-list">
          <li class="todo" v-for="(item, index) in list" v-bind:key="item">
            <div class="view">
              <span class="index">{{ index + 1 }}.</span>
              <label>{{ item }}</label>
              <button class="destroy" @click="remove(index)"></button>
            </div>
          </li>
        </ul>
      </section>
      <footer class="footer">
        <span class="index" v-if="list.length!=0"><strong>{{ list.length }}</strong> Items left </span>
        <button class="clear" @click="clear" v-show="list.length!=0">Clear</button>
      </footer>
    </section>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  // components: {
  //   HelloWorld
  // },
  // data(){
  //   return{
  //     arr:[
  //       {name:'张三丰'},{name:'袁泉'}
  //     ]
  //   }
  //   },
  //   methods:{
  //     add:function(){
  //       this.arr.push({name:'高圆圆'})
  //     },
  //     remove:function(){
  //       this.arr.shift();
  //     }
  //   }

  // methods:{
  //   doIt:function(p1,p2,p3){
  //     alert(p1+"，"+p2+"，"+p3+"?");
  //   },
  //   ok:function(){
  //     alert('账号不存在！（这是v-on点击事件）');
  //   }
  // }

  // data(){
  //   return{
  //     message:"v-model获取和设置表单元素的值（双向数据绑定）"
  //   }
  // },
  // methods:{
  //   getM:function(){
  //     alert(this.message);
  //   },
  //   setM:function(){
  //     this.message = '我是改变后的message值哟~'
  //   }
  // }

  //我的记事本案例
  data() {
    return {
      list: ["画画", "吃饭", "睡觉"],
      inputValue:"好好学习，天天向上"
    };
    
  },
  methods:{
      add:function(){
        this.list.push(this.inputValue);
      },
      remove:function(index){
        this.list.splice(index,1);
      },
      clear:function(){
        this.list=[];
      }
    } 
};
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
.note {
  width: 500px;
  margin: 0 auto;
}
input {
  width: 100%;
  height: 64px;
  background-color: #42b88329;
  border: 0;
  outline: 0;
  border-bottom: 1px solid #42b883d0;
  font-style: italic;
  font-size: 20px;
  padding-left: 16px;
  box-sizing: border-box;
}
h1 {
  font-size: 32px;
  color: #42b883;
}
.main {
  width: 100%;
}
ul {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
li {
  position: relative;
  list-style: none;
  width: 100%;
  height: 64px;
  line-height: 64px;
  background-color: #42b88329;
  border-bottom: 1px solid #42b883d0;
}
.view {
  padding: 0 16px;
}
.view span,
.view label {
  float: left;
  font-size: 20px;
}
.view .destroy {
  display: none;
  position: absolute;
  right: 16px;
  top: 20px;
  width: 20px;
  height: 20px;
  background-color: #42b883;
  border: none;
}
ul li:hover .destroy {
  display: block;
}

.footer {
  display: flex;
  justify-content: space-between;
  height: 64px;
  line-height: 64px;
  background-color: #42b88329;
  padding: 0 12px;
  color: #42b883;
  font-weight: 700;
}

.footer .clear { 
  border: none;
  background: none;
  color: #42b883;
  font-weight: 700;
  font-size: 16px;
}
</style>

