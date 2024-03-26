<script>
import ModalView from './components/ModalView.vue'

export default {
  data() {
    return {
      title: "Vue Modal",
      desc: "click on the below button",
      bool: false,
      showModal: false,
      // modalTitle: "Modal Title",
      // modalContent: "This data content is passed by a Prop",
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
    toggleModal() {
      this.showModal = !this.showModal
    }

  }
}
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ title }}</h1>
  <h1>{{ desc }}</h1>
  <h2 v-if="showModal">Modal added to the DOM</h2>
  
  <teleport to='#modal' >  
    <ModalView
      v-if="showModal"
      theme="dark"
      @close="toggleModal"
    >
    <template v-slot:links>
      <a href="#">Sign Up Now!</a>
      <a href="#">More Information</a>
    </template>
    <h1>Modal Title</h1>
    <p>This data content is passed by a Prop</p>
    </ModalView>
  </teleport>

  <button @click="toggleModal">Show Modal</button>
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
</style>
