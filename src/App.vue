<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to My First Demo Vue.js App"/>
    <ListItems msg="App Content List"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ListItems from './components/ListItems'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ListItems
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
