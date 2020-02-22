<template>
  <div id="hey">
    <h3>Nice to meet you, {{name}}</h3>
    <input v-model="name" />
    <h4>**Love might happen in the most unexcepted place and time ? **</h4>
    <div>
      <button class="unvote" v-on:click="disagree">Disagree</button>
      <code>{{vote}}</code>
      <button class="vote" v-on:click="agree">Agree</button>
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
        return "Ask again later";
      } else if (this.vote < 0) {
        return "Don't count on it!";
      } else {
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
  text-align: center;
}
button {
  border-radius: 5px;
  width: 150px;
}
.unvote {
  background-color: black;
  color: white;
  border-radius: 50px;
  background: linear-gradient(225deg, #1f1f1f, #242424);
  box-shadow: -24px 24px 48px #121212, 24px -24px 48px #323232;
}
.vote {
  background-color: #30ff99;
  color: black;
  border-radius: 50px;
  background: linear-gradient(45deg, #6da838, #5c8d2f);
  box-shadow: 24px -24px 48px #36531c, -24px 24px 48px #96e74c;
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