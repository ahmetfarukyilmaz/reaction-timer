<template>
  <h1>Test Your Reflexes !</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <ClickBlock v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
import ClickBlock from "./components/ClickBlock.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: { ClickBlock,Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      showResults: false,
      score: null,
    };
  },
  methods: {
    start() {
      this.delay = 1500 + Math.random() * 3000;
      this.isPlaying = true;
      this.showResults = false;
    },

    endGame(reactionTime) {
      this.showResults = true;
      this.score=reactionTime
      this.isPlaying=false
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
    color: #444;
    margin-top: 60px;
  }
  button {
    background: #0faf87;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
  }
  button[disabled] {
    opacity: 0.2;
    cursor: not-allowed;
  }
</style>
