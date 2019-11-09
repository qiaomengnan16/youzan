<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide swp-page" v-for="list in lists">
        <a class="js-no-follow" v-bind:href="list.clickUrl">
          <img class="goods-main-photo fadeIn" :src="list.img" />
        </a>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
</template>

<style>
.swiper-slide img {
  height: 100%;
  width: 100%;
}
</style>
  
<script>
import Swiper from "swiper";
import "swiper/dist/css/swiper.css";

export default {
  name: "swipe",
  // // props: ['lists']
  props: {
    lists: {
      type: Array,
      required: true
    },
    name: {}
  },
  created() {
    // console.log(document.querySelectorAll('.swiper-slide'))
  },
  mounted() {
    // console.log(document.querySelectorAll('.swiper-slide'))
    new Swiper(".swiper-container", {
      loop: true,
      // If we need pagination
      pagination: {
        el: ".swiper-pagination"
      },
      // Navigation arrows
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev"
      },
      // And if we need scrollbar
      scrollbar: {
        el: ".swiper-scrollbar"
      }
    });
  }
  // watch: {
  //   lists(val, oldVal){
  //     console.log(val, oldVal)
  //     console.log(document.querySelectorAll('.swiper-slide'))
  //     this.$nextTick(()=>{
  //       console.log(document.querySelectorAll('.swiper-slide'))
  //     })
  //   }
  // }
};
</script>

