<template>
  <h1>Reaction Timer</h1>
  <button @click="play">Play</button>
  <Banner @end="showResult" :delay="delay" v-if="isPlaying" />
  <Results v-if="result" :result="result" />
</template>

<script>
import Banner from "./components/Banner.vue";
import Results from "./components/Result.vue";

export default {
  components: { Banner, Results },
  data() {
    return {
      result: 0,
      isPlaying: false,
      delay: 0,
    };
  },
  methods: {
    showResult(result) {
      this.result = result;
      this.isPlaying = false;
      this.delay = 0;
    },
    play() {
      this.result = 0;
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
  },
};
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  padding: 10px 20px;
  background-color: aquamarine;
  border: none;
  border-radius: 5px;
  color: cornflowerblue;
  cursor: pointer;
}
</style>
