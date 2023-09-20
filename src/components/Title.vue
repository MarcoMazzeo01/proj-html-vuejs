<script>
export default {
  props: ["isBig"],
};
</script>

<template>
  <h6><slot></slot></h6>
</template>

<style lang="scss" scoped>
h6 {
  color: $opaque-white;
  text-transform: uppercase;
  font-family: $poppins-font;
  font-weight: 200;
  transform: scaleY(0.85);
  margin: 0;
}

h6::before {
  content: "";
  width: 30px;
  margin-right: 10px;
  background-color: $main-accent2;
  height: 1.5px;
  display: inline-block;
  position: relative;
  top: -5px;
}
</style>
