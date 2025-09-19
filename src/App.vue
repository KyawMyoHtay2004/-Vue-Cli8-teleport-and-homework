<template>
  <h1 ref="greet">Hi {{ title }}i</h1>
  <div v-if="showModal">
    <Modal :theme="theme" @close="showModal = false">
      <h2>Login success</h2>
      <p>welcome user kyaw myo htay</p>
    </Modal>
  </div>
  <div v-if="showDelete">
    <Modal :theme2="theme2" @close2="showDelete = false">
      <h2>Are you sure?</h2>
      <p>Do you want to delete this item?</p>
    </Modal>
  </div>
  <!-- <button @click="clickHandler">Click</button> -->
  <button @click="showModal = true">Open modal</button><br />
  <button @click="showDelete = true">Open delete modal</button>
</template>

<script>
import Modal from "./components/CustomModal.vue";
export default {
  data() {
    return {
      title: "Vue 3",
      header: "Login success",
      content: "Welcome user kyaw myo htay",
      theme: "success",
      theme2: "delete",
      showModal: false,
      showDelete: false,
    };
  },
  components: {
    Modal,
  },
  methods: {
    clickHandler() {
      this.$refs.name.focus();
      this.$refs.greet.textContent = "Hello ";
    },
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
h2 {
  color: white;
}
</style>
