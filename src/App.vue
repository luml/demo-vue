<template>
  <div id="app" :class="modeClass">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to the simplest Demo Vue.js App" />
    <ListItems msg="App Content Docs" arr="ABC" buttons="abc" alert="I warn you Jimmy!" />
    <HeyThere person="Jimmy" />
    <label class="checkbox">
      <input type="checkbox" v-model="darkMode">
      Dark Mode
    </label>
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
  },
  data() {
    return {
      darkMode: false
    }
  },
  computed: {
    modeClass(){
      return this.darkMode ? 'dark-mode' : 'light-mode';
    }
  },
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
}
/* .light-mode h1, h3, p {
  color: black;
} */
.dark-mode {
  background: #000;
  color: #bbb;
}
.dark-mode h1, h3, p {
  color: #bbb;
}
</style>