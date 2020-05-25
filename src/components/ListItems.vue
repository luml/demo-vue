<template>
  <div id="list">
    <h3>{{msg}}</h3>
    <div class="linkList">
      <ul v-for="count in arr" :key="count">
        <li>
          <a
            v-bind:href="href"
            v-bind:class="{ active: isActive }"
            v-on:click="go"
          >Go doc{{count}}</a>
      </li>
    </ul>
    </div>
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
import routes from '../routes'

export default {
  name: "ListItems",
  props: {
    msg: String,
    arr: [String],
    buttons: [String],
    href: {
      type: String,
      required: true
    }
  },
  computed: {
    isActive() {
      return this.href === this.$root.currentRoute
    }
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
    },
    go(event) {
      event.preventDefault()
      this.$root.currentRoute = this.href
      window.history.pushState(
        null,
        routes[this.href],
        this.href
      )
    }
  },
  data() {
    return {
      bs: ['blur', 'contrast', 'brightness'],
      tbd: `We are gonna skew a picture`
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 0;
}
.linkList {
  display: flex;
  flex-direction: row;
  justify-content: center;
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
.active {
  color: cornflowerblue
}
</style>
