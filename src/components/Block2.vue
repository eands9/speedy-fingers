<template>
  <h2 class="block2" v-if="showBlock">
      Click Me!
  </h2>
</template>

<script>
export default {
    props: ['scoreProps'],
    data() {
        return {
            showBlock: false,
            timer: null
        }
    },
    mounted() {
        setTimeout(() => {
             this.showBlock = true;
        },this.scoreProps)
    }
}
</script>

<style>
    .block2 {
        color: white;
        background: green;
        margin: 40px auto;
        text-align: center;
        padding: 100px 0;
        border-radius: 20px;
        width: 400px;
    }
</style>