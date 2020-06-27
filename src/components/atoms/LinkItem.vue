<template>
  <li>
    <a :href="href"><slot /></a>
  </li>
</template>

<script>
export default {
  props: {
    href: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: #fff;
}
</style>
