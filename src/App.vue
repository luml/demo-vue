<template>
  <div id="app" :class="modeClass">
    <img alt="Vue logo" src="./images/nordwood-themes-nqPe1juwcdQ-unsplash.jpg" style="width: 60%" />
    <HelloWorld msg="Welcome to the simplest Demo Vue.js App" />
    <ListItems msg="Postcard collection" arr="123" />
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
      darkMode: false,
      currentRoute: window.location.pathname
    }
  },
  computed: {
    modeClass() {
      return this.darkMode ? 'dark-mode' : 'light-mode';
    }
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
  transition: all 0.5s ease-in-out;
}
/* Have to style two times for color h3 and p element under light mode */
.light-mode h3 {
  color: black;
}
.light-mode p {
  color: black;
}
.dark-mode {
  background: #000;
  color: #bbb;
  margin: -1rem;
}
.dark-mode h1, h3, p {
  color: #bbb;
}
</style>