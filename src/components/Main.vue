<script>
import Title from "./Title.vue";
import Button from "./Button.vue";
import Carousel from "./Carousel.vue";

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

  components: { Title, Button, Carousel },
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

  <!-- * ABOUT US * -->
  <section id="about">
    <div class="left"></div>
    <div class="right">
      <div class="container">
        <Title>About Us</Title>
        <h2>We make your strategy work</h2>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nemo labore
          assumenda alias repudiandae cumque, fugit maiores odio. Enim ipsam
          aspernatur accusamus impedit esse? Perferendis rem doloremque
          inventore fugiat, tenetur molestias? Dolores in excepturi dicta eius
          autem nam ipsa exercitationem at assumenda dolor sequi, dignissimos
          optio? Illum temporibus odio, eligendi corrupti.
        </p>
      </div>
    </div>
  </section>

  <!-- banner -->
  <div class="banner">
    <div
      class="container d-flex justify-content-center align-items-center gap-4"
    >
      <h2>We help to deliver the business case</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi modi
        numquam adipisci non esse ipsa. Ex corporis quaerat maiores quam non
        iste recusandae. Facere esse harum excepturi placeat quibusdam non!
      </p>
    </div>

    <div class="banner__button">
      <Button bgColor="secondary">get started</Button>
    </div>
  </div>

  <!-- * PROJECTS * -->
  <section id="projects">
    <div class="container">
      <Title>Projects</Title>
      <h2>How our consultants helped our costumers</h2>
      <Carousel />
    </div>
  </section>

  <!-- * TESTIMONIALS * -->
  <section id="testimonials">
    <div class="container-fluid">
      <div class="container mb-4">
        <Title>Testimonial</Title>
        <h2>What our costumers say about us</h2>
      </div>

      <div class="row bg-white d-flex justify-content-center">
        <div class="col-3 p-5" v-for="n in 3" :key="n">
          <blockquote>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
              totam quam et! Dicta eaque odit assumenda voluptatem a magni
              aliquam exercitationem at, doloremque consequatur veniam debitis
              dolorem deleniti sapiente eveniet.
            </p>
          </blockquote>
          <h4>Vera Duncan</h4>
          <p class="mb-0">Amazon Inc.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- * BLOG * -->
  <section id="blog">
    <div class="container">
      <Title>Blog</Title>
      <div class="d-flex justify-content-between align-items-center">
        <h2>Recent news you can't miss</h2>
        <Button bgColor="primary">View All</Button>
      </div>

      <div class="posts_container container d-flex gap-4">
        <div class="blog__post">
          <img
            src="images/startup-business-people-and-strategy-board-PAJ3P9K-1390x1042.jpg"
            alt="blog_pic"
          />

          <div class="post__description">
            <span>July 4, 2019 by Paul</span>
            <h3>Canadian Consulting Firm acquired by UK giant</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis
              facilis quia dignissimos laboriosam soluta sit illo non labore,
              unde magnam aperiam exercitationem officia accusamus deserunt
              animi, aliquid quisquam nam illum.
            </p>
          </div>
        </div>

        <div class="blog__post">
          <img
            src="images/business-people-working-together-on-project-and-5FHSKBL-1390.jpg"
            alt="blog_pic"
          />

          <div class="post__description">
            <span>July 4, 2019 by Paul</span>
            <h3>Canadian Consulting Firm acquired by UK giant</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis
              facilis quia dignissimos laboriosam soluta sit illo non labore,
              unde magnam aperiam exercitationem officia accusamus deserunt
              animi, aliquid quisquam nam illum.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
$bg-color: #22213c;

h2 {
  font-family: $titles-font;
  color: $opaque-white;
  text-transform: uppercase;
  font-size: 2em;
  font-weight: 500;
  line-height: 0.9em;
}

// CONSULTING SECTION
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
  width: 67%; //non so come far toccare il margine della pagina senza rompere tutto
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

// ABOUT US SECTION
#about {
  min-height: 100vh;
  display: flex;

  .left {
    background-color: $secondary-accent1;

    flex-basis: 60%;
    background-image: url("images/business-people-working-together-on-project-and-5FHSKBL.jpg");
  }

  .right {
    @include solid_gradient;
    flex-basis: 40%;
    color: $translucent-white2;
    display: flex;
    align-items: center;
    padding: 0 4em;
  }
}

.banner {
  background-color: $main-accent2;
  position: relative;
  padding: 5em 0;

  p {
    flex-basis: 50%;
    text-align: justify;
  }

  h2 {
    color: $dark-blue;
    font-size: 2em;
    flex-basis: 30%;
  }

  .banner__button {
    position: absolute;
    z-index: 500;
    bottom: 0;
    right: 0;
  }
}

// BLOG SECTION
#blog {
  background-color: $bg-color;
  padding: 4em 0;
  padding-bottom: 6em;

  .blog__post {
    width: 50%;
    position: relative;
    object-fit: contain;

    img {
      max-width: 100%;
    }

    .post__description {
      background-color: $opaque-white;
      width: 70%;
      position: absolute;
      z-index: 100;
      bottom: -15%;
      right: 0;
      padding: 1em 2em;

      h3 {
        font-size: 1.5em;
        font-family: $titles-font;
      }

      p {
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        overflow: hidden;
      }

      span {
        color: $secondary-accent2;
        font-size: 0.8em;
        font-family: $poppins-font;
        font-weight: 300;
      }
    }
  }
}

.posts_container {
  margin-top: 3em;
}

#testimonials {
  background-color: $bg-color;
  padding-top: 4em;

  h4 {
    font-family: $titles-font;
    margin: 0;
  }
}

#testimonials .row > .col-3:hover {
  background-image: url("images/oliver-ragfelt-488196-2.jpg");
  background-position: center;
  background-size: cover;
  color: white;
}

blockquote > p {
  color: $dark2;
}

.col-3:hover blockquote > p {
  color: white;
}

// PROJECTS \ PORTFOLIO
#projects {
  background-color: $dark-blue;
  padding-top: 5em;
  padding-bottom: 3em;
}
</style>
