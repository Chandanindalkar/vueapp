<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <h1>{{ desc }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>
  <h2 v-if="bool">CSS class added to the ref element</h2>
</template>

<script>

export default {
  data() {
    return {
      title: "Template Refs",
      desc: "click on the below input field",
      bool: false
    }
  },
  name: 'App', // optional
  components: {

  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.bool = !this.bool
    },

  }
}
</script>
 
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.active {
  background-color: aquamarine;
  border-color: blue;
  color: blue;
  border-width: 10px;
}
</style>
