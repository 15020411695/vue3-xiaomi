<template>
    <!-- <div>{{ num }}</div>
    <div v-text="num"></div>
    <div v-text="obj"></div>
    <div>{{ obj.name }}{{ obj.age }}</div>
    <div v-text="`${obj.name}--${obj.age}`"></div>
    <div></div> -->
    <!-- <ul>
      <li v-for="(item) in links" v-bind:key="item.id">
        <a v-bind:href="item.url" v-text="item.name"></a>
      </li>
    </ul>
    <div v-show="isLogin===false">欢迎</div>
    <button v-show="isLogin===true">登录</button>
  
    <span v-if="score >= 90">优秀</span>
    <span class="abc" v-else-if="score >= 80">良好</span>
    <span v-else-if="score >=70">中等</span>
    <span v-else-if="score >=60">及格</span>
    <span v-else>不及格</span>
  
    <span v-text="sex?'男':'女'"></span> -->
  
    <!-- <button v-on:click="clickHandler">点击</button>
    <button v-on:click="clickHandler2($event,55)">按钮2</button>
    <button v-on:click="clickHandler3(66)">按钮3</button> -->
  <!-- <div>
    <span v-bind:class="{active:index===1}" v-on:click="index = 1">tab1</span>
    <span v-bind:class="{active:index===2}" v-on:click="index = 2">tab2</span>
    <span v-bind:class="{active:index===3}" v-on:click="index = 3">tab3</span>
  </div>
  <div>
    <div v-show="index===1">tab1内容</div>
    <div v-show="index===2">tab2内容</div>
    <div v-show="index===3">tab3内容</div>
  </div> -->
  <input type="text" v-bind:value="name" v-on:inpput="inputHandler">
  <input type="text" v-model="addr">
  <input name="hobby" type="checkbox" v-bind:value="1" v-model="hobby">吃饭
  <input name="hobby" type="checkbox" v-bind:value="2" v-model="hobby">睡觉
  <input name="hobby" type="checkbox" v-bind:value="3" v-model="hobby">打豆豆
  
  <input name="sex" type="radio" value="man" v-model="sex">男
  <input name="sex" type="radio" value="woman" v-model="sex">女
  </template>
  
  <script setup>
    import {ref} from 'vue';
    const name = ref("");
    const inputHandler = (e)=>{
      name.value = e.target.value;
    }
  const addr = ref("上海");
  
  const hobby = ref([])
  const sex = ref('man')
    // const index = ref(1);
    // const sex = ref('man')
  
  
  </script>
  
  <style>
    .active {
      color: red;
    }
  </style>