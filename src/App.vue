<template>
  <h1 ref="greet">Hi {{ title }}i</h1>
  <input type="text" ref="name" />
  <button @click="clickHandler">Click</button>
  <Modal />
</template>

<script>
import Modal from "./components/CustomModal.vue";
export default {
  data() {
    return {
      title: "Vue 3",
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
