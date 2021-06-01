<template>
  <nav>
    <img
      class="nav-item"
      src="@/assets/images/logo.png"
      alt="logo"
      width="100"
      height="35"
    />
    <nav-text
      class="nav-item align-self-center"
      text1="Deliver to"
      text2="Pakistan"
      style="text-align: right"
    >
      <template #prefix-icon>
        <icon icon="map-marker-alt" />
      </template>
    </nav-text>
    <Search class="nav-item" />
    <Lang class="nav-item" />
    <Account class="nav-item" />
    <nav-text class="nav-item" text1="Returns" text2="& Orders" />
  </nav>
</template>

<script>
import NavText from "@/components/NavText";
import Search from "@/components/Search";
import Lang from "@/components/Lang";
import Account from "@/components/Account";
export default {
  components: {
    NavText,
    Search,
    Lang,
    Account,
  },
};
</script>
<style scoped>
nav {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background: black;
}
.nav-item {
  padding: 10px;
}
</style>


<style lang="scss" scoped>
 @use '@/assets/scss/_variables.scss' as v;
  nav {
    // background: slate;
  }
</style>
