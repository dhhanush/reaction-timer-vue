<template>
  <p>The score is {{ result }}</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["result"],
  computed: {
    rank() {
      if (this.result < 250) {
        return "Ninja Fingers";
      } else if (this.result < 400) {
        return "Rapid Reflexes";
      } else {
        return "...Snail Pace";
      }
    },
  },
};
</script>

<style>
.rank {
  font-weight: bold;
  color: aquamarine;
  font-size: 2em;
}
</style>
