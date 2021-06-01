<template>
  <div class="nav-text-wrapper">
    <span class="line-1">{{ text1 }}</span>
    <span class="line-2"
      >
      
      <slot class="icon-slot" name="prefix-icon"></slot>
      {{ text2 }}
      <slot class="icon-slot" name="suffix-icon"></slot>
    </span>
  </div>
</template>

<script>
export default {
  props: ["text1", "text2"],
};
</script>

<style scoped>
.nav-text-wrapper {
    color: white;
}
.nav-text-wrapper .line-1 {
  font-size: 12px;
  display: block;
}
.nav-text-wrapper .line-2 {
  font-size: 14px;
  display: block;
  font-weight: bolder;
}
.icon-slot {
  margin-left: 5px;
}
</style>
