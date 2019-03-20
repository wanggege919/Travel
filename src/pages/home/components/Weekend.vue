<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul >
            <li class="item" v-for='item in weekendList' :key='item.id'>
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="item-text"> 
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
                
            </li>
        </ul>
    </div>    
</template>
<script>
export default {
    name:'HomeWeekend',
    props: {
        weekendList: Array
    },
    data(){
        return {
            // recommendList:[
            //     {
            //         "id": "0001",
            //         "imgUrl": "http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg",
            //         "title": "北京温泉排行榜",
            //         "desc": "细数北京温泉，温暖你的冬天"
            //     }
            // ]
        }
    }
}
</script>
<style lang='stylus' scoped>
@import '../../../assets/styles/mixins.styl'
    .title
        line-height: .8rem
        background #eee
        text-indent .2rem
    .item
        // display flex
        // height 3.8rem
        // padding .3rem
        border-bottom  1px solid #eee
        .item-img-wrapper
            overflow hidden
            width 100%
            height 0
            padding-bottom 33.9%
            background red
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
                font-size .30rem
                padding .2rem 0
                ellipsis()
            .item-desc
                font-size .24rem
                color #bbb
                padding-bottom .3rem
                ellipsis()
</style>
