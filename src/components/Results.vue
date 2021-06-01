<template>
  <p>Reaction Time: {{ scoreProps }} ms</p>
  <p class="feed">{{ feed }}</p>
</template>

<script>
export default {
  props: ["scoreProps"],
  data() {
    return {
      feed: null,
    };
  },
  mounted() {
    if (this.scoreProps < 400) {
      this.feed = "Speedy Fingers!";
    } else if (this.scoreProps < 880) {
      this.feed = "All Right!";
    } else {
      this.feed = "Ubinay..";
    }
  },
};
</script>

<style>
.feed {
  font-size: 2.3rem;
  color: #0faf87;
  font-weight: 50;
}
</style>
