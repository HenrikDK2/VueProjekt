<template>
  <article>
    <List>
      <li>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </li>

      <li>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </li>

      <li>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </li>
    </List>
  </article>
</template>

<script>
import Img from "../atoms/Img";
import List from "../atoms/List";

export default {
  name: "IndexGrid",
  components: {
    List,
    Img
  }
};
</script>

<style scoped lang="scss">
article {
  margin: 100px 0;
  padding: 0 2rem;
  & > ul {
    display: grid;
    grid-auto-rows: 400px;
    place-content: center;
    grid-gap: 50px;
    grid-template-columns: repeat(auto-fit, minmax(200px, 400px));
    & figure {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
