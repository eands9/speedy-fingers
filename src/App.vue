<template>
  <h1>Kyle Reaction Timer KH13 EH6</h1>
  <button @click="start">Play</button>
  <Block @click="msgFoul" v-if="isPlaying" :blockMsgP="blockMsg" :delayProps="delay"></Block>
  <h2 class="blockRed" v-if="isPlaying">{{ blockMsg }}</h2>
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: { Block },
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
     console.log(this.delay)
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
.blockRed {
    color: white;
    background: red;
    margin: 40px auto;
    text-align: center;
    padding: 100px 0;
    border-radius: 20px;
    width: 400px;
}
</style>
