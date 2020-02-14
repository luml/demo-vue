<template>
  <div id="hey">
    <h3>Nice to meet you, {{name}}</h3>
    <h4>Love might happen in the most unexcepted place and time</h4>
  </div>
</template>

<script>
export default {
  name: "HeyThere",
  props: {
    name: String
  }
};
</script>