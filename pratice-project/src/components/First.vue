<template>
  <div class="first">
    <p>{{message}}</p>
  </div>
</template>

<script>
  export default {
    name: "first",
    data() {
      return {
        message: 'Tis is first component practice'
      }
    }
  }
</script>

<style scoped>
  .first p {
    color: red;
    font-size: 30px;
    font-weight: bold;
  }
</style>
