<template>
  <div v-show="visible" class="dropdown-wrapper">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ["visible"],
};
</script>

<style lang="scss" scoped>

.dropdown-wrapper {
  position: absolute;
  left: 0;
  top: 90%;
  min-width: 240px;
  padding: 10px;
  // box-shadow: 0 2px 4px 0 rgb(0 0 0 / 13%);
  background: #fff;
  border: 1px solid #bbb;
  border-radius: 3px 3px 3px 3px;
    &::before {
      content: '';
      position: absolute;
      top: -20px;
      border: 10px solid #fff;
      border-top-color: transparent;
      border-right-color: transparent;
      border-left-color: transparent;
      }
}
</style>
