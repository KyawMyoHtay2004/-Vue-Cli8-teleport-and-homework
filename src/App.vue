<template>
  <h1 ref="greet">Hi {{ title }}i</h1>
  <input type="text" ref="name" />
  <button @click="clickHandler">Click</button>
</template>

<script>
export default {
  data() {
    return {
      title: "Vue 3",
    };
  },
  methods: {
    clickHandler() {
      this.$refs.name.focus();
      this.$refs.greet.textContent = "Hello ";
    },
  },
};
</script>

<style>
h1 {
  color: red;
}
</style>
