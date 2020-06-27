<template>
  <ul>
    <slot />
  </ul>
</template>

<script>
export default {
  name: "List",
};
</script>

<style scoped>
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
