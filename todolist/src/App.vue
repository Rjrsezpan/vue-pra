<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <MyHeader msg="This is a vue practice"/>
    <MyHeader :msg="title"/>
    <List @myMsg="getData"/>
  </div>
</template>

<script>
  // import HelloWorld from './components/HelloWorld'
  import List from './components/List'
  import MyHeader from './components/MyHeader'

  export default {
    name: 'App',
    components: {
      List, MyHeader
    },
    data() {
      return {
        title: 'Vue study'
      }
    },
    methods: {
      getData(msg) {
        console.log(msg)
        this.title = msg
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
