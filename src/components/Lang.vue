<template>
  <div class="lang-wrapper" @click="showDropDown = !showDropDown" @mouseenter="showDropDown = true" @mouseleave="showDropDown = false">
    <img src="@/assets/images/usa-flag.png" alt="flag" width="25" height="20" />
    <icon icon="caret-down" class="caret-down-icon"/>
    <drop-down :visible="showDropDown">
      <p>Change Language <small class="primary-clr">Learn More</small></p>
      <div
        class="lang-iterator"
        v-for="(l, i) in langs"
        :key="i"
        @mouseover="l.checked = true"
        @mouseout="l.checked = false"
      >
        <hr v-if="i === 1" />
        <input
          type="radio"
          name="en"
          :checked="l.checked"
          :id="l.lang"
          :value="l.lang"
        />
        <label :for="l.lang"> {{ l.label }}</label>
      </div>
      <hr />
      <p>Change Currency <small class="primary-clr">Learn More</small></p>
      <p>$ - USD - U.S. Dollar <small class="primary-clr">Change Currency</small></p>
      <hr />
      <p>
        <img
          src="@/assets/images/usa-flag.png"
          alt="flag"
          width="10"
          height="10"
        />

        You are shopping on Amazon.com
      </p>
      <div style="text-align: center">
        <a href="#">Change country/region</a>
      </div>
    </drop-down>
  </div>
</template>

<script>
import DropDown from "@/components/DropDown";
export default {
  components: {
    DropDown,
  },
  data() {
    return {
      showDropDown: false,
      langs: [
        { checked: true, lang: "en", label: "English - EN" },
        { checked: false, lang: "esp", label: "Español - ES" },
        { checked: false, lang: "tr", label: "简体中文 - ZH" },
        { checked: false, lang: "de", label: "Deutsch - DE " },
        { checked: false, lang: "pt", label: "Português - PT" },
        { checked: false, lang: "zh", label: "繁體中文 - ZH" },
        { checked: false, lang: "ko", label: "한국어 - KO" },
        { checked: false, lang: "he", label: "עברית - HE" },
        { checked: false, lang: "ar", label: "اللغة العربية - AR" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>

@import "@/assets/scss/_variables.scss";
@import "@/assets/scss/global.scss";

.lang-wrapper {
  cursor: pointer;
  position: relative;
  color: $link-inactive-clr;
  font-size: 13px;
}
.lang-iterator:hover {
  text-decoration: underline;
  color: $link-active-clr;
}
</style>
