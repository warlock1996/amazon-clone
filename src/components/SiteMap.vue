<template>
  <div class="sitemap-wrapper">
    <div class="sitemap-wrapper__linkbox">
      <div class="sitemap-wrapper__item" v-for="(n, i) in links" :key="i">
        <div class="sitemap-wrapper__item__heading">
          {{ n.text }}
        </div>
        <div class="sitemap-wrapper__item__list">
          <ul>
            <li v-for="(cn, ci) in n.children" :key="ci">{{ cn.text }}</li>
          </ul>
        </div>
      </div>
    </div>
    <hr>
    <div class="sitemap-wrapper__buttons">
        <img src="@/assets/images/logo.png" alt="logo" width="80">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          text: "Get to Know Us",
          children: [
            { text: "Careers", link: "#" },
            { text: "Blog", link: "#" },
            { text: "About Amazon", link: "#" },
            { text: "Investor Relations", link: "#" },
            { text: "Amazon Devices", link: "#" },
            { text: "Amazon Tours", link: "#" },
          ],
        },
        {
          text: "Make Money with Us",
          children: [
            { text: "Careers", link: "#" },
            { text: "Blog", link: "#" },
            { text: "About Amazon", link: "#" },
            { text: "Investor Relations", link: "#" },
            { text: "Amazon Devices", link: "#" },
            { text: "Amazon Tours", link: "#" },
          ],
        },
        {
          text: "Amazon Payment Products",
          children: [
            { text: "Careers", link: "#" },
            { text: "Blog", link: "#" },
            { text: "About Amazon", link: "#" },
            { text: "Investor Relations", link: "#" },
            { text: "Amazon Devices", link: "#" },
            { text: "Amazon Tours", link: "#" },
          ],
        },
        {
          text: "Let Us Help You",
          children: [
            { text: "Careers", link: "#" },
            { text: "Blog", link: "#" },
            { text: "About Amazon", link: "#" },
            { text: "Investor Relations", link: "#" },
            { text: "Amazon Devices", link: "#" },
            { text: "Amazon Tours", link: "#" },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/_variables.scss";

.sitemap-wrapper {
  background-color: $footer-bg;
  color: $navbar-clr;
  &__linkbox {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    column-gap: auto;
    padding: 50px 10px;
    margin: auto 200px;
  }
  &__item {
    &__heading {
      font-size: 21px;
      font-weight: 500;
    }
    &__list {
      ul {
        list-style-type: none;
        padding: 0;
        li {
          font-weight: 200;
          font-size: 14px;
          line-height: 25px;
          &:hover {
            cursor: pointer;
            text-decoration: underline;
          }
        }
      }
    }
  }
  hr {
      border-color: #cccccc36;
  }
  &__buttons {
      padding: 20px 0px;
      display: flex;
      justify-content: center;
  }
}
</style>
