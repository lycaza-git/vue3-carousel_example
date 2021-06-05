<template>
  <carousel :items-to-show="1">
    <slide v-for="slide in dataslide" :key="slide">
      <component v-bind:is="slide" />
    </slide>

    <template #addons>
      <navigation />
      <pagination />
    </template>
  </carousel>
</template>

<script>
// If you are using PurgeCSS, make sure to whitelist the carousel CSS classes
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
import test from "./test1.vue";
import test2 from "./test2.vue";

export default {
  name: "App",
  data() {
    return {
      dataslide: [test, test2, 3, 4],
    };
  },
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
};
</script>