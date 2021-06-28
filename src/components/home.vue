<template>
  <swiper :pagination="true" class="mySwiper">
  <swiper-slide><img src="image/banner01.jpg" alt=""></swiper-slide>
  <swiper-slide><img src="image/banner02.jpg" alt=""></swiper-slide>
  <swiper-slide><img src="image/banner03.jpg" alt=""></swiper-slide>
  <swiper-slide><img src="image/banner04.jpg" alt=""></swiper-slide>
  </swiper>
  <div class="container mb-4">
    <h2 class="text-center mt-5">BEST 상품</h2>
      <p class="text-center mt-3 mb-5 font">인기 상품을 소개합니다.</p>
    <div class="row">
      <div class="col-sm-6 col-md-3 text-center mb-5 p-2 imgwrap" v-for="(item,i) in 4" :key="i">
        <img :src="pdata[i].image" alt="" class="w-100 p-1">
        <div class="mt-1" @click="$emit('pOpen',pdata[i].id)">{{pdata[i].title}}</div>
      </div>
      <div class="btn btn-primary m-auto d-block" style="width:100px"><router-link to="/product">more</router-link></div>
    </div>
  </div>

</template>

<script>

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
import "swiper/components/pagination/pagination.min.css"

// Import Swiper styles
import 'swiper/swiper.scss';

// import Swiper core and required modules
import SwiperCore, {
  Pagination
} from 'swiper/core';

// install Swiper modules
SwiperCore.use([Pagination]);
export default {
  props:['pdata'],
  components: {
    Swiper,
    SwiperSlide,
  },

 
}
</script>

<style>
.imgwrap:hover { transform:scale(1.1); transition:0.3s; }
.font { color:#555; }
.best h2:after { content:""; width: 30px; height: 1px; background: pink; display: block; margin: 0 auto; }
</style>