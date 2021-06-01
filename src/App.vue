<template>
  <h1>Speedy Fingers</h1>
  <button @click="start">Play</button>
  <Block
    v-if="isPlaying"
    :blockMsgP="blockMsg"
    :delayProps="delay"
    @end="endGame"
  ></Block>
  <Results v-if="showResults" :scoreProps="score" />
  <h2 @click="msgFoul" class="blockRed" v-if="showRed">{{ blockMsg }}</h2>
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      isTimerRunning: false,
      blockMsg: "",
      delay: null,
      showRed: false,
      score: 0,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.blockMsg = "Don't click yet... Wait for it!";
      this.showRed = true;
      this.delay = 2000 + Math.random() * 5000;
      this.disableRedBlock();
      console.log(this.delay);
    },
    msgFoul() {
      this.isPlaying = false;
      this.blockMsg =
        "Foul! Pls don't click until I turn green... Click Play to restart";
    },
    disableRedBlock() {
      setTimeout(() => {
        if (this.isPlaying === false) {
          console.log("firstif");
        } else {
          console.log("elseif");
          this.showRed = false;
          // this.isPlaying = false;
        }
      }, this.delay);
    },
    endGame(reactiontimeEM) {
      this.score = reactiontimeEM;
      this.isPlaying = false;
      this.showResults = true;
      console.log(this.score);
    },
  },
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
