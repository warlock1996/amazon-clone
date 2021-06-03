<template>
  <div class="carousel-wrapper">
    <div v-for="n in 5" :key="n">
      <transition name="slidein">
        <img
          v-show="slide == n"
          :src="require(`@/assets/images/Fuji_TallHero (${n}).jpg`)"
          alt="slide_image"
        />
      </transition>
    </div>
    <div class="products-grid-wrapper">
      <template v-for="(n, i) in products" :key="i">
        <product-card :heading="n.heading" :show-link="n.link">
          <img
            :src="require(`@/assets/images/${n.image}.jpg`)"
            alt="product_image"
          />
        </product-card>
      </template>
    </div>
  </div>
</template>

<script>
import ProductCard from "@/components/ProductCard.vue";

export default {
  components: {
    ProductCard,
  },
  data() {
    return {
      slide: 1,
      speed: 5000,
      slideInterval: null,
      products: [
        { heading: "Beauty Picks", link: true, image: "beauty" },
        { heading: "Get a fit at home", link: true, image: "fit" },
        { heading: "Amazon Basics", link: true, image: "basics" },
        { heading: "Computer & Accessories", link: true, image: "computer" },
        { heading: "Find your ideal TV", link: true, image: "tv" },
        { heading: "Electronics", link: true, image: "electronics" },
      ],
    };
  },
  mounted() {
    // this.slideInterval = setInterval(() => {
    //   if (this.slide === 5) {
    //     this.slide = 0;
    //   }
    //   this.slide++;
    // }, this.speed);
  },
  beforeUnmount() {
    clearInterval(this.slideInterval);
  },
};
</script>

<style lang="scss" scoped>
.carousel-wrapper {
  div {
    position: relative;
  }
}
.slidein-enter-from,
.slidein-leave-to {
  opacity: 0;
}
.slidein-enter-active,
.slidein-leave-active {
  transition: opacity 1s ease-in-out;
}

.products-grid-wrapper {
  position: absolute;
  display: block;
  bottom: 300px;
  display: grid;
  justify-content: center;
  grid-template-columns: repeat(auto-fill, 350px);
  gap: 15px;
  grid-auto-rows: auto;
  img {
    width: 300px;
    height: auto;
  }
}
</style>
