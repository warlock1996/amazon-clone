<template>
  <header>
    <nav-bar></nav-bar>
  </header>
  <main>
    <router-view />
  </main>
  <footer></footer>
</template>

<script>
import NavBar from "@/components/NavBar";
export default {
  components: {
    NavBar,
  },
};
</script>

<style lang="scss">

@import "@/assets/scss/global.scss";

@font-face {
  font-family: Ember;
  src: url("./assets/fonts/Amazon-Ember-Regular.ttf");
}
body {
  margin: 0;
  font-family: Ember;
}
</style>
