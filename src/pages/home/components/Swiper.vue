<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide v-for='item of swiperList'>
          <img  class="swiper-img" :src="item.imgUrl" key="item.id">
      </swiper-slide>
     
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeSwiper",
  data(){
      return {
          swiperOption:{
              pagination: '.swiper-pagination',
              loop: true,
              autoplay: 3000
          },
          swiperList:[
              {
                  id: '0001',
                  imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ed5f4115226306e48e6fad106a038afe.jpg_750x200_64df48d6.jpg'
              },
              {
                  id: '0002',
                  imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/980adfa646fede8d7a4c46feabaac6ee.jpg_750x200_63ecd371.jpg'
              },
              {
                  id: '0003',
                  imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/2f5f3ea4698c9b7898db7562d89b91ed.jpg_750x200_bd3b4ce9.jpg'
              }
          ]
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
        padding-bottom 26.67%
        background #eee
        .swiper-img
            width 100%
</style>
