<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swp-page swiper-slide" v-for="list in lists">
        <a class="js-no-follow" v-bind:href="list.clickUrl">
          <img class="goods-main-photo fadeIn" :src="list.image">
        </a>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
</template>
<style>
.swiper-slide img {
  width: 100%;
  height: 100%;
}
.swiper-pagination-bullet{
  width: 4px;
  height: 4px;
}
</style>

<script>
import Swiper from "swiper";
import "swiper/dist/css/swiper.css";

export default {
  name: "swipe",
  props: {
    lists: {
      type: Array,
      required: true
    },
    name: {}
  },
  created() {},
  mounted() {
    new Swiper(".swiper-container", {
      loop: true,
      pagination: {
        el: ".swiper-pagination"
      },
      autoplay: {
        delay: 2000
      },
       speed: 2000,
    });
  }
};
</script>



