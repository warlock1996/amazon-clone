<template>
  <div class="product-card-wrapper">
    <div class="product-card-wrapper__heading">
      {{ heading }}
    </div>
    <div class="product-card-wrapper__image">
      <slot></slot>
    </div>
    <div v-if="showLink" class="product-card-wrapper__shoplink">
      <a href="#">
        Shop Now
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["heading", "showLink"],
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/_variables.scss";

.product-card-wrapper {
  display: flex;
  flex-direction: column;
  background: $navbar-clr;
  padding: 10px;
  &__heading {
    font-size: 21px;
    font-weight: 700;
  }
  &__image {
    flex-grow: 1;
  }
  &__heading,
  &__image,
  &__shoplink {
    padding: 5px;
  }
}
</style>
