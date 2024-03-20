<script>
export default {
  props: ['modalTitle', 'modalContent', 'theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}

</script>

<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal"
      :class="{dark: theme === 'dark'}"
    >
      <h1>{{ modalTitle }}</h1>
        <p>{{ modalContent }}</p>
    </div> 
  </div>
</template>

<style scoped>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
  }
  /* any modal that also has the sale class */
  .modal.dark {
    background-color: rgb(71, 71, 71);
    color: rgb(228, 228, 228);
  }
</style>