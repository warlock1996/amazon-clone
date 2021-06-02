<template>
  <div
    class="accounts-wrapper"
    @click="showDropDown = !showDropDown"
    @mouseenter="showDropDown = true"
    @mouseleave="showDropDown = false"
  >
    <nav-text text1="Hello, Sign in" text2="Account & lists">
      <template #suffix-icon>
        <icon icon="caret-down" class="caret-down-icon" />
      </template>
    </nav-text>
    <drop-down :visible="showDropDown">
      <div class="account-card">
        <div class="account-card-item">
          <button class="account-btn">Sign in</button>
          <div>
            <small class="link-inactive-clr"
              >New Customer ?
              <a class="link-active-clr" href="#">Start here</a></small
            >
          </div>
        </div>
        <div class="account-card-item flex">
          <div class="account-list">
            <div>
              <b class="link-inactive-clr">Your List</b>
            </div>
            <ul>
              <li v-for="(i, k) in yourListLinks" :key="k">
                <a href="#"> {{ i.label }}</a>
              </li>
            </ul>
          </div>
          <div class="your-account">
            <div>
              <b class="link-inactive-clr">Your Account</b>
            </div>
            <ul>
              <li v-for="(i, k) in accountLinks" :key="k">
                <a href="#"> {{ i.label }}</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </drop-down>
  </div>
</template>

<script>
import DropDown from "@/components/DropDown";
import NavText from "@/components/NavText";
export default {
  components: {
    DropDown,
    NavText,
  },
  data() {
    return {
      showDropDown: false,
      yourListLinks: [
        { label: "Create a List" },
        { label: "Find a List or Registry" },
        { label: "AmazonSmile Charity Lists" },
      ],
      accountLinks: [
        { label: "Account" },
        { label: "Orders" },
        { label: "Recommendations" },
        { label: "Browsing History" },
        { label: "Watchlist" },
        { label: "Kindle Unlimited" },
        { label: "Content & Devices" },
        { label: "Subscribe & Save Items" },
        { label: "Memberships & Subscriptions" },
        { label: "Music Library" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/global.scss";

.accounts-wrapper {
  position: relative;
}
.account-card {
  display: flex;
  flex-direction: column;
  padding: 15px;
  text-align: center;
  .account-card-item {
    border-bottom: 1px solid #eee;
    .account-btn {
      @extend .amazon-button;
      width: 100%;
      line-height: 30px;
      margin-bottom: 10px;
    }
  }
  .account-card-item.flex {
    display: flex;
    text-align: left;
  }
}
.account-list {
  border-right: 1px solid #eee;
}
.account-list,
.your-account {
  padding: 10px;
}
.account-list ul,
.your-account ul {
  padding: 0;
  list-style-type: none;
  li {
    font-size: 13px;
    a {
      text-decoration: none;
      &:hover {
        text-decoration: underline;
      }
    }
  }
}
</style>
