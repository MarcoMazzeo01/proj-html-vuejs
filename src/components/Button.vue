<script>
export default {
  data() {
    return {
      colors: ["primary", "secondary", "footer"],
    };
  },

  props: {
    bgColor: {
      type: String,
      default: "#ffffff", // Default color if no color is passed
    },
  },

  props: ["bgColor"],

  methods: {
    setButton(color) {
      return this.colors.includes(color) ? color : "";
    },
  },
};
</script>
<template>
  <button type="button" :class="setButton(bgColor)">
    <slot></slot>
  </button>
</template>
<style lang="scss" scoped>
button {
  font-family: $poppins-font;
  text-transform: uppercase;
  font-weight: 300;
  border: none;
  padding: 0.7em 2em;
  cursor: pointer;
}

.primary {
  background-color: $main-accent1;
  color: $dark-blue;
}

.primary:hover {
  background-color: $secondary-accent1;
  color: $opaque-white;
}

.secondary {
  background-color: $secondary-accent1;
  color: $opaque-white;
}

.footer {
  background-color: $dark-blue;
  color: $opaque-white;
}
</style>
