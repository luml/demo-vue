<template>
  <div id="list">
    <h3>{{msg}}</h3>
    <ul v-for="count in arr" :key="count">
      <li>
        💚
        <!-- how to imply Vue router -->
        <a href="/docs/doc_1.html">Go to doc {{count}}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ListItems",
  props: {
    msg: String,
    arr: [String]
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
</style>
