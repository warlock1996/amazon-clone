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
    <hr />
    <div class="sitemap-wrapper__buttons">
      <img src="@/assets/images/logo.png" alt="logo" width="80" />
      <button class="amazon-btn-outline">
        <icon icon="globe" />
        <span>
          English
        </span>
      </button>
      <button class="amazon-btn-outline">
        <icon icon="dollar-sign" />
        <span>
          USD- U.S. Dollar
        </span>
      </button>
      <button class="amazon-btn-outline">
        <img
          src="@/assets/images/usa-flag.png"
          alt="flag"
          width="25"
          height="20"
        />
        <span>
          United States
        </span>
      </button>
    </div>
    <div class="sitemap-wrapper__servicebox">
      <div class="sitemap-wrapper__servicebox__list">
        <template v-for="(mn, mi) in 4" :key="mi">
          <ul>
            <li v-for="(n, i) in service" :key="i">
              <span class="lineOne">
                {{ n.text }}
              </span>
              <span class="lineTwo">
                {{ n.subtext }}
              </span>
            </li>
          </ul>
        </template>
      </div>
      <div class="sitemap-wrapper__servicebox__links">
        <ul>
          <li v-for="(n, i) in footerbarlinks" :key="i">
            {{ n }}
          </li>
        </ul>
      </div>
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
      service: [
        { text: "Amazon Music", subtext: "Stream millions of songs" },
        { text: "Sell on Amazon", subtext: "Start a selling account" },
        {
          text: "Book Depository",
          subtext: "Book with Free Delivery Worldwide",
        },
        { text: "IMDb", subtext: "Movies, TV & Celebrities" },
        { text: "Ring", subtext: "Smart Home Security Systems" },
      ],
      footerbarlinks: [
        "Conditions of Use",
        "Privacy Notice",
        "Interest-Based Ads",
        "© 1996-2021, Amazon.com, Inc. or its affiliates",
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
    padding: 30px 0;
    margin: auto 10px;
    display: flex;
    justify-content: center;
  }
  &__servicebox {
    background: $service-box-bg;
    &__links {
      ul {
        list-style-type: none;
        margin: 0;
        padding: 10px;
        text-align: center;
        li {
          display: inline;
          font-size: 11px;
          padding: 5px;
        }
      }
    }
  }
  &__servicebox__list {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    column-gap: auto;
    padding: 50px 10px;
    margin: auto 200px;

    ul {
      margin: 0;
      padding: 0;
      list-style-type: none;
      li {
        line-height: 30px;
        .lineOne {
          display: block;
          font-size: 11px;
        }
        .lineTwo {
          font-size: 10px;
          color: #ccc;
        }
      }
    }
  }
}
.amazon-btn-outline {
  margin-left: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: transparent;
  outline: none;
  border: 1px solid #ccc;
  color: $navbar-clr;
  border-radius: 4px;
  padding: 5px;
}
</style>
