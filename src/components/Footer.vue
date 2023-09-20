<script>
import Button from "./Button.vue";

export default {
  data() {
    return {};
  },

  components: { Button },
};
</script>

<template>
  <footer>
    <div class="jumbotron">
      <div
        class="container d-flex justify-content-center align-items-center flex-column"
      >
        <h2>Let's talk about work</h2>
        <p class="w-50 text-center mb-4">
          Talented, brilliant, incredible, amazing, show stopping, spectacular,
          never the same, totally unique, completely not ever been done
          before...
        </p>
        <Button bgColor="footer">Get Started</Button>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.jumbotron {
  background-image: url("images/business-people-working-together-on-project-and-B3MZ4TX.jpg");
  color: $opaque-white;
  padding: 5em 0;

  h2 {
    font-family: $titles-font;
    text-transform: uppercase;
    font-weight: 700;
    font-size: 2.2em;
  }
}
</style>
