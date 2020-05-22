<template>
  <div id="list">
    <h3>{{msg}}</h3>
    <ul v-for="count in arr" :key="count">
      <li>
        💚
        <a href="/docs/doc_1.html">Go to doc {{count}}</a>
      </li>
    </ul>
    <div class="button-area">
      <div v-for="but in buttons" :key="but">
        <button v-on:click="alertYou">{{but}}</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ListItems",
  props: {
    msg: String,
    arr: [String],
    buttons: [String],
    alert: String
  },
  methods: {
    alertYou() {
      window.alert(this.alert)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 0.5rem;
}
a {
  color: #42b983;
}
button {
  width: 3rem;
  height: 1.5rem;
  border-radius: 0.5rem;
  background: #42b983;
  background: linear-gradient(90deg, #42b983, #42e983);
}
.button-area {
  display: flex;
  justify-content: center;
}
.button-area>div {
  margin: 0.2rem;
}
</style>
