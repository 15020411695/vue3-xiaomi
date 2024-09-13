<template>
    <button @click="show = !show">按钮</button>
    <transition name="opacity">
      <div class="box" v-show="show"></div>
    </transition>
    <transition name="scale">
      <div class="box" v-show="show"></div>
    </transition>
  
  </template>
  
  <script setup>
    import {ref} from 'vue'
    const show = ref(true)
  </script>
  
  <style>
    .box {
      width: 100px;
      height: 100px;
      background-color: blue;
    }
    .opacity-enter-active {opacity: 0; transition:all 3s}
    .opacity-enter-to {opacity: 1;}
    .opacity-leave-active {opacity: 1; transition:all 3s;}
    .opacity-leave-to {opacity: 0;}
  
    .scale-enter-active {scale: 0; transition:all 3s}
    .scale-enter-to {scale: 1;}
    .scale-leave-active {scale: 1; transition:all 3s;}
    .scale-leave-to {scale: 0;}
  </style>
  