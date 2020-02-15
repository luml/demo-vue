<template>
  <div id="hey">
    <h3>Nice to meet you, {{name}}</h3>
    <input v-model="name" />
    <h4>**Love might happen in the most unexcepted place and time**</h4>
    <div>
      <button v-on:click="disagree">Disagree</button>
      <code>{{ opinion }}</code>
      <button v-on:click="agree">Agree</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeyThere",
  props: {
    name: String,
    opinion: String,
    methods: {
      disagree: function() {
        this.opinion = "You think?"
      },
      agree: function() {
        this.opinion = "You kidding!"
      }
    }
  }
};
</script>

<style scoped>
h3 {
  margin-bottom: 0;
}
h4 {
  color: #42b983;
  font-style: italic;
}
input {
  margin-top: 10px;
  padding: 0.3rem;
}
button {
  border-radius: 5px;
  width: 150px;
}
</style>