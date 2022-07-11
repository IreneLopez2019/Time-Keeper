<template>
    <!-- <button class="primary-button"><slot></slot></button> -->
    <button class="primary-button">{{label}}</button>
</template>

<script>
export default {
  name: "NuxtTutorial",
  props: ["label"]
};
</script>

<style lang="scss" scoped>
.primary-button {
  min-width: 80px;
  padding: 10px;
  border: none;
  border-radius: 4px;
  color: #fff;
  background-color: #3b847f;
  transition: ease-in-out 0.4s;

  &:active,
  &:hover {
    background: #316d69;
  }
}
</style>