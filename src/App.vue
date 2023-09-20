<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  data() {
    return {
      menuItems: {
        Home: "#",
        About: "#about",
        Projects: "#projects",
        Services: "",
        Blog: "",
        Contact: "#contact",
      },
    };
  },

  components: { Header, Main, Footer },
};
</script>

<template>
  <Header :headerMenu="menuItems" />
  <Main />
  <Footer :footerMenu="menuItems" />

  <div class="floating_buttons">
    <button type="button" class="go-up">
      <a href="#header"
        ><font-awesome-icon icon="fa-solid fa-arrow-up-long " size="xs"
      /></a>
    </button>

    <button type="button" class="support">
      <font-awesome-icon icon="fa-solid fa-comment" />
    </button>
  </div>
</template>

<style lang="scss">
@import "./assets/scss/style.scss";

p {
  font-weight: 300;
}

.floating_buttons {
  position: fixed;
  z-index: 666;
  bottom: 10px;
  right: 10px;

  button {
    aspect-ratio: 1;
    border: 0;
    border-radius: 100%;
    margin: 0 5px;
  }

  .go-up {
    width: 25px;
    background-color: $opaque-white;

    a {
      color: $black;
      text-decoration: none;
    }
  }

  .support {
    width: 45px;
    color: $opaque-white;
    background-color: $navy-blue;
  }
}

// ! SCROLLBAR ! //
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
