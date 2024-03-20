<script>
import ModalView from './components/ModalView.vue'

export default {
  data() {
    return {
      title: "Vue Modal",
      desc: "click on the below input field",
      bool: false,
      modalTitle: "Modal Title",
      modalContent: "This data content is passed by a Prop",
    }
  },
  name: 'App', // optional
  components: {
    ModalView
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

<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <h1>{{ desc }}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button>
  <h2 v-if="bool">Modal added to the DOM</h2>

  <ModalView 
    v-if="bool"
    :modalTitle="modalTitle"
    :modalContent="modalContent"
    @click="handleClick"
  ></ModalView>
</template>
 
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
</style>./components/ModalView.vue
