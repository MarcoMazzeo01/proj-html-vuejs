<script>
export default {
  data() {
    return {
      images: [
        {
          title: "DRY Project",
          img: "DRY-1-790x592",
          category: "Social",
          showDesc: false,
        },
        {
          title: "Purinky Products",
          img: "221bf0b7-8134-43bb-936a-5acbe42db64a-790x592",
          category: "Branding",
          showDesc: false,
        },
        {
          title: "Verizon",
          img: "z1el4c4p-790x592",
          category: "Website",
          showDesc: false,
        },
      ],

      currentIndexes: [0, 1, 2],
    };
  },

  methods: {
    nextImg() {
      let lastIndex = this.currentIndexes.length - 1;
      let nextIndex = this.currentIndexes[lastIndex] + 1;

      // If the next index exceeds the images length, reset it to 0
      if (nextIndex > this.images.length - 1) {
        nextIndex = 0;
      }

      // Shift all current indexes to the left (removing the first index)
      this.currentIndexes.shift();

      // Add the next index to the end of the array
      this.currentIndexes.push(nextIndex);
    },

    prevImg() {
      // Remove the last index from the currentIndexes
      this.currentIndexes.pop();

      // Calculate the previous index
      let firstIndex = this.currentIndexes[0];
      let prevIndex = firstIndex - 1;

      // If the previous index is less than 0, set it to the last index of the images array
      if (prevIndex < 0) {
        prevIndex = this.images.length - 1;
      }

      // Add the previous index to the start of the array
      this.currentIndexes.unshift(prevIndex);
    },
  },

  created() {
    console.log(this.currentIndexes);
  },
};
</script>
<template>
  <div class="arrows">
    <button type="button" @click="prevImg">
      <font-awesome-icon icon="fa-solid fa-arrow-left-long" />
    </button>
    <button type="button" @click="nextImg">
      <font-awesome-icon icon="fa-solid fa-arrow-right-long" />
    </button>
  </div>

  <div class="carousel d-flex">
    <template v-for="(imgIndex, index) in currentIndexes">
      <div
        class="carousel__content"
        @mouseenter="images[imgIndex].showDesc = true"
        @mouseleave="images[imgIndex].showDesc = false"
      >
        <img
          :src="'images/' + images[imgIndex].img + '.jpg'"
          alt="{{ images[imgIndex].title }}"
          :class="images[imgIndex].showDesc ? 'filter' : ''"
        />
        <div class="description" v-show="images[imgIndex].showDesc">
          <h3>{{ images[imgIndex].title }}</h3>
          <p>{{ images[imgIndex].category }}</p>
        </div>
        <!-- <p class="debug">{{ index }}</p> -->
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

    .filter {
      filter: invert(30%) sepia(50%) saturate(675%) hue-rotate(-30deg)
        brightness(70%) contrast(170%);
    }

    .description {
      position: absolute;
      bottom: 0;
      padding: 1em;

      p,
      h3 {
        color: $opaque-white;
        margin: 0;
      }

      h3 {
        font-family: $poppins-font;
        font-size: 1.15em;
        font-weight: 700;
      }

      p {
        font-size: 0.9em;
      }
    }
  }

  //debug class
  .debug {
    color: green;
    position: absolute;
    background-color: white;
    top: 0;
    font-size: 4em;
    font-weight: 700;
  }
}

.arrows {
  display: flex;
  gap: 5px;
  margin: 1em 0;
  justify-content: end;

  button {
    color: $opaque-white;
    background-color: #36354b;
    border: 0;
    font-size: 0.8em;
    padding: 0.5em;
  }
}
</style>
