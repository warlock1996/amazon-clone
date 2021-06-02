<template>
  <div class="secondary-navbar-wrapper">
    <ul class="inline-nav">
      <li @click="showSideBar = true"><icon icon="bars" /> All</li>
      <li>Today's Deals</li>
      <li>Customer Service</li>
      <li>Gift Cards</li>
      <li>Registry</li>
      <li class="grow">Sell</li>
      <li>Amazon's response to COVID-19</li>
    </ul>
    <side-bar :visible="showSideBar" @clickBackDrop="showSideBar = false">
      <div class="sidebar-banner">
        <icon
          class="sidebar-banner__items"
          style="font-size: 19px"
          icon="user-circle"
        />
        <div class="sidebar-banner__items">Hello, Sign In</div>
      </div>
      <div class="sidebar-vmenu-wrapper">
        <template v-for="(m, i) in sideBarMenu" :key="i">
          <div class="sidebar-vmenu-wrapper__heading">{{ m.text }}</div>
          <ul v-if="m.children.length">
            <li v-for="(cm, ci) in m.children" :key="ci">
              <span>{{ cm.text }}</span>
              <icon icon="chevron-right" />
            </li>
          </ul>
          <hr />
        </template>
      </div>
    </side-bar>
  </div>
</template>

<script>
import SideBar from "@/components/SideBar";
export default {
  components: {
    SideBar,
  },
  data() {
    return {
      showSideBar: false,

      sideBarMenu: [
        {
          text: "Digital Content & Devices",
          children: [
            { text: "Amazon Music", link: "#" },
            { text: "Kindle E-readers & Books", link: "#" },
            { text: "Appstore for Android", link: "#" },
          ],
        },
        {
          text: "Shop By Department",
          children: [
            { text: "Electronics", link: "#" },
            { text: "Computers", link: "#" },
            { text: "Smart Home", link: "#" },
            { text: "Arts & Crafts", link: "#" },
          ],
        },
        {
          text: "Programs & Features",
          children: [
            { text: "Gift Cards", link: "#" },
            { text: "#FoundItOnAmazon", link: "#" },
            { text: "Amazon Live", link: "#" },
            { text: "International Shipping", link: "#" },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/global.scss";
@import "@/assets/scss/_variables.scss";

.secondary-navbar-wrapper {
  background: $navbar-sec-bg;
  padding: 5px;
  ul.inline-nav {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    li {
      &.grow {
        flex-grow: 1;
      }
      cursor: pointer;
      font-size: 14px;
      padding: 5px;
      color: $navbar-clr;
      display: inline;
    }
  }
}

.sidebar-banner {
  display: flex;
  justify-content: center;
  align-items: center;
  background: $navbar-sec-bg;
  color: $navbar-clr;
  font-weight: 700;
  &__items {
    font-size: 19px;
    padding: 12px;
  }
}

.sidebar-vmenu-wrapper {
  &__heading {
    font-size: 19px;
    font-weight: 700;
    color: $navbar-sec-bg;
    padding: 10px 30px;
  }
  hr {
    border-color: #eaeded;
  }
  ul {
    padding: 0;
    list-style-type: none;
    li {
      display: flex;
      justify-content: space-between;
      align-items: center;
      line-height: 30px;
      padding: 5px 30px;
      color: $navbar-sec-bg;
      &:hover {
        cursor: pointer;
        background: #eaeded;
      }
    }
  }
}
</style>
