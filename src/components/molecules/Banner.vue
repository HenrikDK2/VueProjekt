<template>
  <article>
    <figure ref="imgContainer">
      <img ref="bottomImg" :class="'hidden'" />
      <img ref="topImg" />
    </figure>

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
    <List ref="buttonList">
      <li v-for="item in bannerImages" :key="item">
        <button @click="clickButton"></button>
      </li>
    </List>
  </article>
</template>

<script>
import List from "../atoms/List";
import LinkItem from "../atoms/LinkItem";

export default {
  data: () => {
    return {
      bannerImages: ["fullscreenImage.jpg", "fullscreenImage2.jpg"],
      buttons: null,
      index: 0
    };
  },
  components: {
    List,
    LinkItem
  },
  methods: {
    clickButton: function(e) {
      if (this.index === this.buttons.indexOf(e.target)) return;
      this.index = this.buttons.indexOf(e.target);

      this.crossFade();
      this.toggleButton();
    },

    crossFade: function() {
      if (this.$refs.bottomImg.classList.contains("hidden")) {
        this.$refs.bottomImg.src = require("@/assets/images/" +
          this.bannerImages[this.index]);
      } else {
        this.$refs.topImg.src = require("@/assets/images/" +
          this.bannerImages[this.index]);
      }

      this.$refs.bottomImg.classList.toggle("hidden");
      this.$refs.topImg.classList.toggle("hidden");
    },

    toggleButton: function() {
      this.buttons.forEach(button => {
        button.classList.remove("activeButton");
      });
      this.buttons[this.index].classList.add("activeButton");
    },

    initial: function() {
      this.buttons = Array.from(
        this.$refs.buttonList.$el.querySelectorAll("button")
      );
      this.toggleButton();
      this.$refs.topImg.src = require("@/assets/images/" +
        this.bannerImages[this.index]);
      this.$refs.bottomImg.src = require("@/assets/images/" +
        this.bannerImages[1]);

      setInterval(() => {
        this.index = this.index + 1;
        if (this.index > this.bannerImages.length - 1) this.index = 0;
        this.crossFade();
        this.toggleButton();
      }, 6000);
    }
  },
  mounted() {
    this.initial();
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

    & ul:first-of-type {
      display: flex;
      justify-content: center;
      align-items: center;
      & > li {
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
  & figure {
    width: 100%;
    padding: 0;
    margin: 0;
    position: relative;
    height: calc(50vh - 80px);
    .hidden {
      opacity: 0;
    }
    & img {
      transition: 1s ease-out opacity;
      opacity: 1;
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      object-fit: cover;
      left: 50%;
      transform: translate(-50%);
    }
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

  & > ul:last-of-type {
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    bottom: 100px;
    left: 50%;
    transform: translate(-50%);
    & > li {
      margin: 0 5px;
    }

    & .activeButton {
      background-color: rgba($color: #ffffff, $alpha: 0.5);
    }

    & button {
      cursor: pointer;
      padding: 0;
      border: none;
      box-shadow: 0 0 2px 0 rgba($color: #696969, $alpha: 0.5);
      background-color: rgba($color: #000000, $alpha: 0.3);
      width: 15px;
      height: 15px;
      border-radius: 50%;
    }
  }
}
</style>
