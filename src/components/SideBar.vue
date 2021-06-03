<template>
  <transition name="slidein">
    <div v-if="visible" class="sidebar-wrapper">
      <icon
        icon="times"
        class="close-sidebar-icon"
        @click="$emit('clickBackDrop')"
      />
      <slot> </slot>
    </div>
  </transition>
  <div v-if="visible" class="backdrop" @click="$emit('clickBackDrop')"></div>
</template>

<script>
export default {
  props: ["visible"],
  emits: ["clickBackDrop"],
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/global.scss";
.sidebar-wrapper {
  position: fixed;
  z-index: 200;
  background: #fff;
  top: 0;
  left: 0;
  height: 100vh;
  overflow-y: scroll;
  width: 25%;
  .close-sidebar-icon {
    position: absolute;
    right: -50px;
    font-size: 30px;
    color: $navbar-clr;
  }
}
.backdrop {
      z-index: 100;
  } 
.slidein-enter-from,
.slidein-leave-to {
  transform: translateX(-250px);
}
.slidein-enter-to,
.slidein-leave-from {
  transform: translateX(0);
}
.slidein-enter-active,
.slidein-leave-active {
  transition: transform 0.2s;
}
</style>
