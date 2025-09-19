<template>
  <h1 ref="greet">Hi {{ title }}i</h1>
  <div v-if="showModal">
    <Modal :theme="theme" @close="showModal = false">
      <h1>Login success</h1>
      <p>welcome user kyaw myo htay</p>
    </Modal>
  </div>
  <!-- <button @click="clickHandler">Click</button> -->
  <button @click="showModal = true">Open modal</button>
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
      showModal: false,
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
</style>
