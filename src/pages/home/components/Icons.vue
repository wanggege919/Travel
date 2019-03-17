<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for='(page,index) of pages' :key = 'index'>
        <div
          class="icon"
          v-for="item of page"
          :key="item.id"
        >
          <div class='icon-img'>
            <img class='icon-img-content' :src='item.iconUrl' />
          </div>
          <p class="icon-description">{{item.discription}}</p>
          
        </div>
        <!-- <div class="swiper-pagination" slot="pagination"></div> -->
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeIcons",
  data(){
      return {
          swiperOption: {
            //   pagination : '.swiper-pagination',
              autoplay: false

          },
          iconList: [
              {
                  id:'0001',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                  discription: '景点门票'
              },
              {
                  id:'0002',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                  discription: '一日游'
              },
              {
                  id:'0003',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                  discription: '郑州必游'
              },
              {
                  id:'0004',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
                  discription: '郑州方特'
              },
              {
                  id:'0005',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
                  discription: '踏青赏花'
              },
              {
                  id:'0006',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
                  discription: '泡温泉'
              },
              {
                  id:'0007',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                  discription: '动植物园'
              },
              {
                  id:'0008',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
                  discription: '亲子游'
              },
              {
                  id:'0009',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
                  discription: '海洋馆'
              },
              {
                  id:'00010',
                  iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png',
                  discription: '当地好玩'
              },

          ]
      }
  },
  computed:{
      pages () {
          const pages = []
          this.iconList.forEach((item,index)=>{
              const page = Math.floor(index / 8)
              if(!pages[page]){
                  pages[page] = []
              }
              pages[page].push(item)
          })
          return pages
      }
  }
};
</script>
<style lang='stylus' scoped>
//   @import '@/assets/styles/varibles.styl'
  @import '../../../assets/styles/varibles.styl'
  @import '../../../assets/styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-description
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkTextColor
        ellipsis()
</style>
