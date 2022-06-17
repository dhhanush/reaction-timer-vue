<template>
  <div v-if="showBlock" class="banner" @click="endGame">click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      timer: null,
      showBlock: false,
      reactionTime: 0,
    };
  },
  methods: {
    startGame() {
      this.showBlock = true;
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    endGame() {
      this.showBlock = false;
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
    },
  },
  mounted() {
    console.log(this.delay);
    setTimeout(() => {
      this.startGame();
      console.log("inside timeout");
    }, this.delay);
  },
};
</script>

<style scoped>
.banner {
  padding: 100px;
  width: 250px;
  border-radius: 20px;
  background-color: aquamarine;
  margin: 20px auto;
  color: pink;
  border: 4px solid pink;
}
</style>
