<template>
  <header>
    <nav>
      <h1>Vendora</h1>
      <List>
        <li>Men</li>
        <li>Women</li>
        <li>Children</li>
      </List>
    </nav>
  </header>
</template>

<script>
import List from "../atoms/List";

export default {
  name: "Header",
  components: {
    List,
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=MuseoModerno:wght@300&display=swap");
nav {
  background: #000;
  display: flex;
  align-items: center;
  height: 80px;
  user-select: none;
  padding: 0 2rem;
  color: #fff;

  & h1 {
    font-size: 2rem;
    margin: 0;
    font-family: "MuseoModerno", cursive;
  }

  & ul {
    display: flex;
    align-items: center;
    margin-left: auto;
    & li {
      cursor: pointer;
      padding: 20px;
      font-size: 1.25rem;
    }
  }
}
</style>
