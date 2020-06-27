<template>
  <article>
    <Img :src="require('@/assets/images/fullscreenImage.jpg')" />
    <div>
      <h2>
        Summer Styles
        <span>50% OFF</span>
      </h2>
      <List>
        <LinkItem :href="'#'">Mens Clothing</LinkItem>
        <LinkItem :href="'#'">Womens Clothing</LinkItem>
      </List>
    </div>
  </article>
</template>

<script>
import Img from "../atoms/Img";
import List from "../atoms/List";
import LinkItem from "../atoms/LinkItem";

export default {
  components: {
    Img,
    List,
    LinkItem
  }
};
</script>

<style scoped lang="scss">
article {
  position: relative;
  white-space: pre;
  & > div {
    position: absolute;
    transform: translate(-50%, -50%);
    left: 50%;
    top: 50%;
  }
  & figure {
    width: 100vw;
    height: calc(50vh - 80px);
  }
  & h2 {
    color: #fff;
    user-select: none;
    text-align: center;
    margin: 0 0 0 0;
    & span {
      display: block;
      font-size: 5rem;
      margin-top: -20px;
    }
  }
  & ul {
    display: flex;
    justify-content: center;
    align-items: center;
    & li {
      margin: 0 20px;
      position: relative;

      &::after {
        content: "";
        position: absolute;
        height: 3px;
        transition: transform ease-in-out 0.3s;
        width: 100%;
        background: #fff;
        bottom: 0;
        left: 0;
        transform: scaleX(0);
      }
      &:hover::after {
        transform: scaleX(0.99);
      }
    }
  }
}
</style>
