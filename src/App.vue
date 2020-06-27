<template>
  <Fragment>
    <Header />
    <main>
      <index />
    </main>
  </Fragment>
</template>

<script>
import { Fragment } from "vue-fragment";
import Index from "./components/pages/Index";
import Header from "./components/organisms/Header";

export default {
  name: "App",
  components: {
    Index,
    Header,
    Fragment,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=MuseoModerno:wght@300&family=Poppins:wght@300;400;500;700&display=swap");

body {
  margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
}
</style>
