<template>
  <header>
    <nav-bar></nav-bar>
    <secondary-nav-bar></secondary-nav-bar>
  </header>
  <main>
    <router-view />
  </main>
  <footer>
    <back-to-top></back-to-top>
    <site-map />
  </footer>
</template>

<script>
import NavBar from "@/components/NavBar";
import SecondaryNavBar from "@/components/SecondaryNavBar";
import SiteMap from "./components/SiteMap.vue";
import BackToTop from "./components/BackToTop.vue";

export default {
  components: {
    NavBar,
    SecondaryNavBar,
    SiteMap,
    BackToTop
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/global.scss";
@import "@/assets/scss/_variables.scss";

@font-face {
  font-family: Ember;
  src: url("./assets/fonts/Amazon-Ember-Regular.ttf");
}
body {
  margin: 0;
  font-family: Ember;
  background: hsl(180, 8%, 92%);
  #app {
    display: flex;
    flex-direction: column;
    main {
      max-width: 1500px;
      flex-grow: 1;
    }
  }
}
</style>
