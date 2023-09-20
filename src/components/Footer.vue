<script>
import Button from "./Button.vue";

export default {
  data() {
    return {};
  },
  props: ["footerMenu"],
  components: { Button },
};
</script>

<template>
  <footer>
    <!-- jumbotron -->
    <section id="footer__jumbotron">
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
    </section>

    <!-- bottom footer -->
    <section id="footer__bottom">
      <div class="container">
        <div class="footer__bottom__upper d-flex justify-content-between">
          <!-- logo -->
          <div class="footer__logo">
            <img src="images/logotype-2-150x25.png" alt="" srcset="" />
          </div>
          <!-- menu -->
          <ul class="menu">
            <li v-for="item in footerMenu">
              <a href="">{{ item }}</a>
            </li>
          </ul>
          <!-- socials -->
          <div class="text-white d-flex gap-4">
            <font-awesome-icon icon="fa-brands fa-instagram" />
            <font-awesome-icon icon="fa-brands fa-linkedin-in" />
            <font-awesome-icon icon="fa-brands fa-facebook-f" />
            <font-awesome-icon icon="fa-brands fa-twitter" />
          </div>
        </div>

        <hr class="my-4" />

        <!-- copyright -->
        <div
          class="footer__bottom__lower d-flex text-secondary justify-content-between"
        >
          <ul>
            <li>Terms of Use</li>
            <li>Privacy Policy</li>
          </ul>

          <p>Copyright &copy; 2020 Phlox Consulting. All Rights Reserved.</p>
        </div>
      </div>
    </section>
  </footer>
</template>

<style lang="scss" scoped>
#footer__jumbotron {
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

#footer__bottom {
  @include solid_gradient;
  padding-top: 4.5em;
  padding-bottom: 1em;
  .menu {
    display: flex;
    gap: 1em;
  }
  .menu > li {
    display: inline-block;

    a {
      text-decoration: none;
      color: $translucent-white2;
      text-transform: uppercase;
    }
  }

  hr {
    border-color: $translucent-white2;
  }
}

ul {
  list-style: none;
  padding: 0;
}
</style>
