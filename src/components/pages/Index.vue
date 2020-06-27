<template>
  <section>
    <Banner />
    <IndexGrid />
  </section>
</template>

<script>
import IndexGrid from "../molecules/IndexGrid";
import Banner from "../molecules/Banner";

export default {
  name: "Index",
  components: {
    IndexGrid,
    Banner,
  },
};
</script>

<style scoped lang="scss"></style>
