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
  <div class="backdrop" @click.self="closeModal">
    <div class="modal"
      :class="{dark: theme === 'dark'}"
    >
      <slot></slot>
      <div class="actions">
        <slot name="links">
          This data is shown when a template is not Passed
        </slot>
      </div>
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
  .modal h1 {
    color: #03cfb4;
    border: none;
    padding: 0;
  }
  .modal p {
    font-style: normal;
  }

  .modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
    color: #333;
  }
  .modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
  }

  /* any modal that also has the sale class */
  .modal.dark {
    background-color: rgb(71, 71, 71);
    color: rgb(228, 228, 228);
  }

  .modal.dark h1 {
    color: white;
  }
  .modal.dark .actions {
    color: white;
  }
  .modal.dark .actions a {
    color: white;
  }
</style>