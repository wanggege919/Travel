<template>
    <div class="header">
        城市选择
        <router-link to='/'>
            <div class="header-left">
                <div class="iconfont left-icon">&#xe63b;</div>
            </div>
        </router-link>
        
    </div>
    
</template>
<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl'
    .header
        position relative
        height .86rem
        line-height .86rem
        text-align center
        background $bgColor
        color #fff
        font-size .30rem
        .header-left
           position absolute
           top 0
           left 0
           width .86rem
           .left-icon
               font-size .5rem
               color #fff
</style>
