<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe63b;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe600;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      城市
      <span class="iconfont arrow-icon">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
    name: 'HomeHeader'
};
</script>
    
<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl'
   .header
      display: flex
      background-color: $bgColor
      height: 0.86rem
      justify-content center
      align-items center
      color #fff
      .header-left
        width: .64rem
        .back-icon
          text-align center
          font-size .5rem
      .header-input
        flex-grow 1
        line-height .64rem
        margin-left .2rem
        border-radius .1rem
        background-color #fff
        color #ccc
        padding-left .2rem
      .header-right
        width: 1.24rem
        text-align center
        .arrow-icon
          margin-left -.1rem
</style>

