<template>
  <div id="list">
    <h3>{{msg}}</h3>
    <ul v-for="count in 3" :key="count">
      <li>{{ count }} 💚</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ListItems",
  props: {
    msg: String
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
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
