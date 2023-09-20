<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  data() {
    return {};
  },

  components: { Header, Main, Footer },
};
</script>

<template>
  <Header />
  <Main />
</template>

<style lang="scss">
@import "./assets/scss/style.scss";

/* Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: #ffffff00 #ffffff00;
}

/* Chrome, Edge and Safari */
*::-webkit-scrollbar {
  width: 5px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

*::-webkit-scrollbar-track:hover {
  background-color: #ffffff00;
}

*::-webkit-scrollbar-track:active {
  background-color: #ffffff00;
}

*::-webkit-scrollbar-thumb {
  border-radius: 5px;
  background-color: $main-accent2;
}

*::-webkit-scrollbar-thumb:hover {
  background-color: $main-accent3;
}

*::-webkit-scrollbar-thumb:active {
  background-color: $secondary-accent1;
}
</style>
