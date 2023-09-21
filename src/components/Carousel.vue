<script>
export default {
  data() {
    return {
      images: [
        "DRY-1-790x592", //dry
        "221bf0b7-8134-43bb-936a-5acbe42db64a-790x592", //sponsorship
        "z1el4c4p-790x592", //vizeon
        "12679",
        "oliver-ragfelt-488196-2",
        "oliver-ragfelt-488196-unsplash",
      ],

      currentIndexes: [0, 1, 2],
    };
  },

  methods: {
    forward() {
      this.currentIndexes.forEach((num, i) => {
        if (this.currentIndexes[i] >= this.images.length - 1) {
          this.currentIndexes[i] = 0;
        } else {
          this.currentIndexes[i] = num + 1;
        }
      });

      console.log(this.currentIndexes);
    },

    back() {
      this.currentIndexes.forEach((num, i) => {
        if (this.currentIndexes[i] == 0) {
          this.currentIndexes[i] = this.images.length - 1;
        } else {
          this.currentIndexes[i] = num - 1;
        }
      });
    },
  },
};
</script>
<template>
  <div class="arrows">
    <button type="button" @click="back">
      <font-awesome-icon icon="fa-solid fa-arrow-left-long" />
    </button>
    <button type="button" @click="forward">
      <font-awesome-icon icon="fa-solid fa-arrow-right-long" />
    </button>
  </div>

  <div class="carousel d-flex">
    <template v-for="(image, index) in images">
      <div class="carousel__content" v-show="currentIndexes.includes(index)">
        <img :src="'images/' + image + '.jpg'" alt="img" />
        <p class="debug">{{ index }}</p>
      </div>
    </template>
  </div>
</template>
<style lang="scss" scoped>
.carousel {
  max-width: 100%;
  gap: 20px;

  .carousel__content {
    width: calc(100% / 3);
    height: auto;
    position: relative;

    img {
      max-width: 100%;
      max-height: 100%;
    }
  }

  .debug {
    color: green;
    position: absolute;
    background-color: white;
    top: 0;
    font-size: 4em;
    font-weight: 700;
  }
}
</style>
