<template>
  <div
    class="accounts-wrapper"
    @click="showDropDown = !showDropDown"
    @mouseenter="showDropDown = true"
    @mouseleave="showDropDown = false"
  >
    <nav-text text1="Hello, Sign in" text2="Account & lists">
      <template #suffix-icon>
        <icon icon="caret-down" style="color: grey; margin-left: 5px" />
      </template>
    </nav-text>
    <drop-down :visible="showDropDown">
      <div class="account-card">
        <div class="account-card-item">
          <button class="amazon-button">Sign in</button>
          <div>
            <small>New Customer ? <a href="#">Start here</a></small>
          </div>
        </div>
        <div class="account-card-item flex">
          <div class="account-list">
            <div>
              <b>Your List</b>
            </div>
            <ul>
              <li v-for="(i, k) in yourListLinks" :key="k">
                <a href="#"> {{ i.label }}</a>
              </li>
            </ul>
          </div>
          <div class="your-account">
            <div>
              <b>Your Account</b>
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

<style scoped>
.accounts-wrapper {
  color: white;
  position: relative;
}
.account-card {
  color: black;
  display: flex;
  flex-direction: column;
  padding: 10px;
  text-align: center;
}
.amazon-button {
  border: 1px solid;
  border-color: #c89411 #b0820f #99710d;
  box-shadow: inset 0 1px 0 0 #fcf3dc;
  background: #f3cf72;
  border-radius: 3px 3px 3px 3px;
  line-height: 30px;
  width: 100%;
}
.amazon-button:hover {
  cursor: pointer;
  background: -webkit-linear-gradient(top, #f6da95, #ecb21f);
}
.account-card-item {
  border-bottom: 1px solid #eee;
}
.account-card-item.flex {
  display: flex;
  text-align: left;
}
.account-list,
.your-account {
  padding: 10px;
}
.account-list ul,
.your-account ul {
  padding: 0;
  list-style-type: none;
}
.account-list ul li a,
.your-account ul li a {
  text-decoration: none;
  color: black;
}
</style>
