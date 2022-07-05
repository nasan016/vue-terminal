<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
<div id="main">
  <div id="terminal">
    <router-view/>
  </div>
</div>
</template>

<style>
@import './assets/base.css';

#main{
  height: 100vh;
  display: flex;
  align-items: center;
  box-sizing: border-box;
  width: 100%;
  overflow-x: hidden;
}

#terminal{
  height: 96.5vh;
  width: 100%;
  border: solid 2px;
  box-shadow: 0 0 10px #9ecaed;
  margin-left: 15px;
  margin-right: 15px;
  border-radius: 4px;
}

</style>
