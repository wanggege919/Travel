<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">您的位置</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>

      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for='item in hotCities' :key = 'item.id'>
            <div class="button">{{item.name}}</div>
          </div>         
        </div>
      </div>

      <div class="area" v-for='(item , key) in cities' :key = 'key' :ref = 'key'>
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item" v-for='innerItem in item' :key='innerItem.id'>
              {{innerItem.name}}
          </div>
        </div>
        
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from "better-scroll"
export default {
  name: "CityList",
  props:{
      hotCities: Array,
      cities: Object,
      letter: String
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch:{
      letter(){
          if(this.letter){
              const element = this.$refs[this.letter][0]
              this.scroll.scrollToElement(element)
          }
      }
  }
};
</script>
<style lang='stylus' scoped>
.border-topbottom {
  &::before {
    border-color: #ccc;
  }

  &::after {
    border-color: #ccc;
  }
}

.list {
  overflow: hidden;
  position: absolute;
  top: 1.52rem;
  right: 0;
  left: 0;
  bottom: 0;

  .title {
    height: 0.62rem;
    line-height: 0.62rem;
    background: #eee;
    text-indent: 0.2rem;
  }

  .button-list {
    display: flex;
    flex-wrap: wrap;
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;

    .button-wrapper {
      box-sizing: border-box;
      width: 33.33%;
      text-align: center;
      padding: 0.12rem;

      .button {
        border: 1px solid #ccc;
        padding: 0.12rem;
        border-radius: 0.06rem;
      }
    }
  }

  .item-list {
    .item {
      height: 0.62rem;
      line-height: 0.62rem;
      border-bottom: 1px solid #ccc;
      text-indent: 0.2rem;
    }
  }
}
</style>
