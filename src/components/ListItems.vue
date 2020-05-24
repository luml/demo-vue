<template>
  <div id="list">
    <h3>{{msg}}</h3>
    <ul v-for="count in arr" :key="count">
      <li>
        💚
        <a href="/docs/doc_1.html">Check postcard {{count}}</a>
      </li>
    </ul>
    <div class="aman"><img src="../images/nordwood-themes-nqPe1juwcdQ-unsplash.jpg" alt="unsplash photo"></div>
    <div class="button-area">
      <div v-for="but in bs" :key="but">
        <button v-on:click="alertYou">{{but}}</button>
      </div>
    </div>
    <p v-html="tbd"></p>
  </div>
</template>

<script>
export default {
  name: "ListItems",
  props: {
    msg: String,
    arr: [String],
    buttons: [String]
  },
  methods: {
    alertYou() {
      switch (event.target.innerText) {
        case 'blur':
          document.querySelector('.aman>img').style.filter = 'blur(3px)'
          break
        case 'contrast':
          document.querySelector('.aman>img').style.filter = 'contrast(150%)'
          break
        case 'brightness':
          document.querySelector('.aman>img').style.filter = 'brightness(0.5)'
          break
      }
    }
  },
  data() {
    return {
      bs: ['blur', 'contrast', 'brightness'],
      tbd: `Here are some a link and buttons don't do anything by far`
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
  width: 5rem;
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
img {
  width: 20%;
  height: auto;
}
</style>
