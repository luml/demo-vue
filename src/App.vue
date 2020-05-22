<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to the simplest Demo Vue.js App" />
    <ListItems msg="App Content Docs" arr="ABC" buttons="abc" alert="I warn you Jimmy!" />
    <HeyThere person="Jimmy" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ListItems from "./components/ListItems";
import HeyThere from "./components/HeyThere";

export default {
  name: "App",
  components: {
    HelloWorld,
    ListItems,
    HeyThere
  }
};
</script>

<style>
body {
  background-color: bisque;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>