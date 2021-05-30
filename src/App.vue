<template>
  <h1>Kyle Reaction Timer KH13 EH6</h1>
  <button @click="start">play</button>
  <Block @click="msgFoul" v-if="isPlaying" :blockMsgP="blockMsg"></Block>
  <Block2 v-if="isTimerRunning" :scoreProps="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Block2 from './components/Block2.vue'

export default {
  name: 'App',
  components: { Block, Block2 },
  data() {
    return {
      isPlaying: false,
      isTimerRunning: false,
      blockMsg: 'Don\'t click yet... Wait for it!',
      delay: null
    }
  },
  methods: {
    start() {
     this.isPlaying = true;
     this.delay = 2000 + Math.random() * 5000;
    },
    msgFoul(){
      this.blockMsg='Foul! Pls don\'t click until I turn green... Click Play to restart'
    }
  }
}
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
