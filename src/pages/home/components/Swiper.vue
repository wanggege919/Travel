<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if='showSwiper'>
      <!-- slides -->
      <swiper-slide v-for='item of swiperList' :key = 'item.id'>
          <img  class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
     
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeSwiper",
  props: {
      swiperList: Array
  },
  data(){
      return {
          swiperOption:{
              pagination: '.swiper-pagination',
              loop: true,
              autoplay: 3000
          },
      }
  },
  computed: {
      showSwiper(){ //解决页面轮播从最后一页开始的bug
          return this.swiperList.length
      }
  }
};
</script>
<style lang='stylus' scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background #fff
    .wrapper
        overflow hidden
        width 100%
        height  0
        padding-bottom 31.25%
        background #eee
        .swiper-img
            width 100%
</style>
