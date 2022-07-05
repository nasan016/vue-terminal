<script setup lang="ts">
import { ref } from 'vue'

import {
  hello,
} from '../components/commands'

const terminal = ref([])
const user_cmd = ref('')

function addLine(cmd : Array<Array<string>>, time : number){
  for(let i = 0; i < cmd.length; i++){
    setTimeout(function(){
          terminal.value.push(cmd[i][0])
    }, time * i)
  }
}

function addTerminalLine(){
  switch(user_cmd.value){
    case 'clear':
      terminal.value = []
      break
    case 'hello':
      addLine(hello, 50)
      break
  }
  user_cmd.value = ''
}

</script>

<template>
<div class="terminal">
  <div v-for="(item, idx) in terminal" :key="idx"><span v-html="item"></span></div>
  <div>hey!<input id="user_input" v-model="user_cmd" @keyup.enter="addTerminalLine"/></div>
</div>
</template>

<style scope>

@keyframes typing{
  from {width: 0}
  to {width: 100%}
}

.terminal{
  padding: 20px;
}
</style>
