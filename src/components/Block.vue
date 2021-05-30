<template>
  <h2 class="block" v-if="showBlock">
      {{ blockMsgP }}
  </h2>
</template>

<script>
export default {
    props: ['blockMsgP'],
    data() {
        return {
            showBlock: false,
        }
    },
    mounted() {
        this.showBlock = true;
    }
}
</script>

<style>
    .block {
        color: white;
        background: red;
        margin: 40px auto;
        text-align: center;
        padding: 100px 0;
        border-radius: 20px;
        width: 400px;
    }
</style>