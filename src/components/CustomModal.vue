<template>
  <div v-if="theme" class="backdrop" @click.self="closeModal">
    <div
      class="modal"
      :class="{ success: theme === 'success', danger: theme === 'delete' }"
    >
      <slot>default</slot>
    </div>
  </div>
  <div v-else-if="theme2" class="backdrop" @click.self="closeModal2">
    <div
      class="modal2"
      :class="{ success: theme2 === 'success', danger: theme2 === 'delete' }"
    >
      <slot>default</slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme", "theme2"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
    closeModal2() {
      this.$emit("close2");
    },
  },
};
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.75);
  width: 100%;
  height: 100%;
}
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
}
.modal2 {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
}
p {
  font-style: normal;
}
.success {
  background-color: green;
  color: white;
}
.danger {
  background-color: crimson;
  color: white;
}
</style>
