<script>
export default {
  data() {
    return {
      logo: "/images/logotype.png",
      menuItems: ["Home", "About", "Projects", "Services", "Blog", "Contact"],
    };
  },
};
</script>

<template>
  <header>
    <nav class="d-flex justify-content-between align-items-center">
      <div>
        <img :src="logo" alt="logo" />
      </div>

      <ul class="menu">
        <li v-for="item in menuItems">{{ item }}</li>
      </ul>
    </nav>

    <div class="jumbotron">
      <div class="jumbotron__inner-container">
        <div>
          <h1>The best business Consulting</h1>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
$menu-height: 80px;

* {
  // outline: 2px dashed white;
}

header {
  position: relative;

  nav {
    position: fixed;
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
  }

  li:hover {
    animation: borderAnimation 0.25s;
    animation-fill-mode: forwards;
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

    div {
      position: relative;
      width: 100%;
      max-width: 100%;
      left: 50%;
      top: 20%;
    }
  }
}

h1 {
  color: $opaque-white;
  font-size: 4.5em;
  text-transform: uppercase;
  font-family: $titles-font;
  font-weight: 600;
}
</style>
