<!-- OrangeButton.vue -->

<template>
  <button class="orange-button" @click="handleClick">New Invoice +</button>
</template>

<script>
export default {
  methods: {
    handleClick() {
      this.$emit("new-invoice-clicked");
    },
  },
};
</script>

<style scoped>
.orange-button {
  background-color: #f17b50;
  color: white;
  margin-top: 8px;
  margin-bottom: 8px;
  padding: 10px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
