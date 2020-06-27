<template>
  <article>
    <List>
      <LinkItem>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </LinkItem>

      <LinkItem>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </LinkItem>

      <LinkItem>
        <Img :src="require('@/assets/images/fullscreenImage2.jpg')" />
      </LinkItem>
    </List>
  </article>
</template>

<script>
import Img from "../atoms/Img";
import List from "../atoms/List";
import LinkItem from "../atoms/LinkItem";

export default {
  name: "IndexGrid",
  components: {
    List,
    LinkItem,
    Img
  }
};
</script>

<style scoped lang="scss">
article {
  margin-top: 100px;
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
