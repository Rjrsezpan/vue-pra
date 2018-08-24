<template>
  <h1>{{title}}-{{msg}}</h1>
</template>

<script>
  export default {
    name: "my-header",
    data() {
      return {
        title: 'This is title...'
      }
    },
    props: {
      msg: {
        type: String,
        default: "Who are you?"
      }
    }
  }
</script>

<style scoped>

</style>
