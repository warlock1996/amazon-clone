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

<style>
  body {
    margin: 0;

  }
</style>
