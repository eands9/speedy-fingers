<template>
  <h2 class="block" v-if="showBlock" >
      Click Me!
  </h2>
</template>

<script>
export default {
    props: ['delayProps'],
    data() {
        return {
            showBlock: false,
            timer: null,
        }
    },
    mounted() {
        setTimeout(() => {
             this.showBlock = true;
        },this.delayProps)
        this.$emit('hideRedBlock')
        console.log(this.delayProps)
    }
}
</script>

<style>
    .block {
        color: white;
        background: green;
        margin: 40px auto;
        text-align: center;
        padding: 100px 0;
        border-radius: 20px;
        width: 400px;
    }
</style>