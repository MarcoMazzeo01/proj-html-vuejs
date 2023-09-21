<script>
import Button from "./Button.vue";
import Title from "./Title.vue";

export default {
  data() {
    return {
      logo: "/images/logotype.png",
      activeItem: "Home",
    };
  },

  props: ["headerMenu"],
  components: { Button, Title },
};
</script>

<template>
  <header id="header">
    <nav class="d-flex justify-content-between align-items-center">
      <div>
        <img :src="logo" alt="logo" />
      </div>

      <ul class="menu">
        <li
          v-for="(link, name, index) in headerMenu"
          :class="activeItem == name ? 'active' : ''"
        >
          <a :href="link" @click="activeItem = name">{{ name }}</a>
        </li>
      </ul>
    </nav>

    <div class="jumbotron">
      <div class="jumbotron__inner-container">
        <div class="jumbotron__container">
          <Title>Always the best way you need it</Title>
          <h1>The best business Consulting</h1>
          <Button bgColor="primary">Read More</Button>
          <div class="playButton">
            <font-awesome-icon :icon="['fas', 'play']" style="color: #39ffbf" />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
$menu-height: 80px;

* {
  outline: 0px dashed white;
}

header {
  position: relative;

  nav {
    position: absolute;
    top: 0;
    width: 100%;
    height: $menu-height;
    z-index: 999;
    padding: 0 5em;

    div {
      flex-basis: 10%;
    }
    div > img {
      width: 100%;
    }
  }
}

.menu {
  list-style: none;
  display: flex;
  gap: 1em;
  height: 100%;
  margin: 0;

  li {
    display: inline-block;
    text-transform: uppercase;
    margin: 0;
    display: flex;
    align-items: center;
    color: $opaque-white;
    font-family: $poppins-font;
    font-weight: 200;

    a {
      color: inherit;
      text-decoration: none;
    }
  }

  li:hover {
    animation: borderAnimation 0.25s;
    animation-fill-mode: forwards;
  }

  .active {
    border-top: 5px solid $opaque-white;
    font-weight: 500;
  }
}

@keyframes borderAnimation {
  0% {
    border-top: 0;
    font-weight: 200;
  }
  100% {
    border-top: 5px solid $opaque-white;
    font-weight: 500;
  }
}

.jumbotron {
  height: 100vh;
  position: relative;
  background-color: $secondary-accent1;
  background-image: url("images/portrait-of-young-architect-woman-on-meeting-KFZCE3A.jpg");
  background-repeat: no-repeat;
  background-position: 430px;

  .jumbotron__inner-container {
    @include solid_gradient;
    height: 100%;
    width: 35%;

    .jumbotron__container {
      position: relative;
      width: 100%;
      max-width: 100%;
      left: 25%;
      top: 30%;
    }
  }
}

h1 {
  color: $opaque-white;
  font-size: 5em;
  text-transform: uppercase;
  font-family: $titles-font;
  font-weight: 600;
  margin-bottom: 0.5em;
  line-height: 0.9em;
}

.playButton {
  margin-left: 2em;
  width: 40px;
  aspect-ratio: 1;
  border: 2px solid $opaque-white;
  border-radius: 100%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
}
</style>
