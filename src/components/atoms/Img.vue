<template>
  <figure>
    <img @dragstart="stopDrag" :alt="alt" :src="src" />
  </figure>
</template>

<script>
export default {
  name: "Img",
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    }
  },
  methods: {
    stopDrag: function(e) {
      e.preventDefault();
    }
  }
};
</script>

<style scoped lang="scss">
figure {
  padding: 0;
  margin: 0;
  & img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
</style>
