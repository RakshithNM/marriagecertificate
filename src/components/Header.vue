<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <h2>{{ subText }}</h2>
    <p class="no-print" style="color: red">This is a development version and in progress, only available for selected people for review</p>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String,
    subText: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
