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
    <Search class="nav-item grow" />
    <Lang class="nav-item" />
    <Account class="nav-item" />
    <nav-text class="nav-item" text1="Returns" text2="& Orders" />
    <nav-text class="nav-item" text2="Cart">
      <template #prefix-icon>
        <icon icon="shopping-cart" class="cart-icon" />
      </template>
    </nav-text>
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

<style lang="scss" scoped>
@import "@/assets/scss/_variables.scss";
@import "@/assets/scss/global.scss";

nav {
  background-color: $navbar-bg;
  color: $navbar-clr;
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  .nav-item {
    padding: 10px;
    cursor: pointer;
    .cart-icon {
      font-size: 30px;
    }
    &.grow {
      flex-grow: 1;
    }
  }
}
</style>
