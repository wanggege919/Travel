<template>
    <div>
        <div class="title">热销推荐</div>
        <ul >
            <li class="item" v-for='item in recommendList' :key='item.id'>
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="item-text"> 
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
                
            </li>
        </ul>
    </div>    
</template>
<script>
export default {
    name:'HomeRecomment',
    props: {
        recommendList: Array
    },
    data(){
        return {

        }
    }
}
</script>
<style lang='stylus' scoped>
@import '../../../assets/styles/mixins.styl'
    .title
        line-height: .8rem
        background #eee
        margin-top .2rem
        text-indent .2rem
    .item
        display flex
        height 1.9rem
        // background yellow
        padding .3rem
        border-bottom  1px solid #eee
        .item-img-wrapper
            overflow hidden
            width 1.9rem
            height 0
            padding-bottom 1.9rem
            .item-img
                width 100%
        .item-text
            min-width 0
            padding-left .2rem
            display flex
            flex 1
            flex-direction column
            align-items flex-start
            justify-content space-around
            .item-title
                font-size .36rem
                ellipsis()
            .item-desc
                font-size .28rem
                color #bbb
                ellipsis()
            .item-button
                background #ff9300
                padding .08rem .15rem
                border-radius .06rem
                color #fff
                font-weight 700
</style>
