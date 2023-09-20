<script>
export default {
  data() {
    return {
      // Consulting
      consultingServices: {
        "Statistical Consulting": "signal",
        "Digital Consulting": "bullhorn",
        "Banking Consulting": "wallet",
        "Enterprise Consulting": "bullseye",
      },
    };
  },
};
</script>

<template>
  <!-- * CONSULTING *  -->
  <section id="consulting">
    <div class="container">
      <h6>Our Consultants can help you</h6>

      <div class="consulting__grid">
        <div
          class="consulting__card"
          v-for="(icon, title, index) in consultingServices"
        >
          <div class="symbol">
            <font-awesome-icon :icon="icon" />
          </div>

          <div>
            <div>
              <h3>{{ title }}</h3>
              <p>
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ipsum
                eligendi nihil ducimus, voluptatum delectus earum porro dolore
                provident alias numquam natus recusandae dolorem quos officiis
                voluptatem iusto quisquam, ratione minima?
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
* {
  //   outline: red solid 1px;
}

#consulting {
  background-color: $opaque-white;
  padding: 6em 0;

  h6 {
    font-family: $titles-font;
    text-transform: uppercase;
    font-weight: 700;
    font-size: 1.7em;
    margin-bottom: 2em;
    position: relative;
  }
}

#consulting h6::after {
  content: "";
  width: 100%;
  margin-left: 10px;
  background-color: $main-accent2;
  height: 1.5px;
  display: inline-block;
  position: absolute;
  z-index: 666;
  top: 50%;
}
.consulting__grid {
  $gap: 5em;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: $gap;

  .consulting__card {
    display: flex;
    flex-basis: calc(100% / 2 - $gap);
    gap: 2em;
    .symbol {
      background-color: $secondary-accent1;
      color: $opaque-white;
      border-radius: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 45px;
      height: 45px;
      aspect-ratio: 1;
    }

    h3 {
      font-family: $titles-font;
      text-transform: uppercase;
      font-size: 1.5em;
      font-weight: 600;
    }

    p {
      color: $dark2;
      font-weight: 300;
    }
  }
}
</style>
