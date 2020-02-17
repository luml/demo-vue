<template>
  <div id="hey">
    <h3>Nice to meet you, {{name}}</h3>
    <input v-model="name" />
    <h4>**Love might happen in the most unexcepted place and time**</h4>
    <div>
      <button v-on:click="disagree">Disagree</button>
      <code>{{vote}}</code>
      <button v-on:click="agree">Agree</button>
    </div>
    <p>Final Vote: {{showVoted}}</p>
  </div>
</template>

<script>
export default {
  name: "HeyThere",
  props: {
    person: {
      type: String
    }
  },
  data() {
    return {
      name: this.person,
      vote: 0
    };
  },
  methods: {
    disagree() {
      this.vote++;
    },
    agree() {
      this.vote--;
    }
  },
  computed: {
    showVoted() {
      if (this.vote > 0) {
        return "You think?";
      } else if (this.vote < 0) {
        return "You're kidding!";
      } else{
        return "There's no answer for this question";
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
code {
  margin: 0 10px;
  font-weight: bold;
  font-style: italic;
  font-size: 20px;
}
p {
  font-weight: bold;
}
</style>