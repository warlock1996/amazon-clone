<template>
  <nav>
      <img class="nav-item" src="@/assets/images/logo.png" alt="logo" width="115" height="50">
      <Deliver class="nav-item" />
      <Search class="nav-item" />
      <Lang class="nav-item" />
      <Account class="nav-item" />
  </nav>
</template>


<script>
import Deliver from "@/components/Deliver"
import Search from "@/components/Search"
import Lang from "@/components/Lang"
import Account from "@/components/Account"
export default {
  components: {
    Deliver,
    Search,
    Lang,
    Account
  }
}
</script>
<style scoped>
  nav {
    display: flex;
    justify-content: flex-start;
    align-items: flex-end;
    background: black;
  }
  .nav-item {
    padding: 12px;
  }
</style>