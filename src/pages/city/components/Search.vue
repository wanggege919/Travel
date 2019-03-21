<template>
    <div>
        <div class="search">
            <input v-model='keyWord' class="search-input" type="text" placeholder="输入城市名或拼音">
        </div>
        <div class="search-list" v-show = 'keyWord' ref = 'search'>
            <ul>
                <li class="search-item" 
                v-for='item in list' 
                :key='item.id'
                >
                    {{item.name}}
                </li>
                <li class="search-item" v-show='hasNoData'>没有找到匹配数据</li>
            </ul>
        </div>
    </div>
    
</template>
<script>
import BScroll from 'better-scroll'
export default {
    name:'CitySearch',
    props:{
        cities: Object
    },
    data(){
        return {
            keyWord: '',
            list: [],
            timer: null
        }
    },
    computed: {
        hasNoData(){
            return !this.list.length
        }
    },
    watch:{
        keyWord(){
            if(this.timer){
                clearTimeout(this.timer)
            }
            if(!this.keyWord){
                this.list = []
                return
            }
            this.timer = setTimeout(()=>{
                const result = []
                for(let i in this.cities){
                    this.cities[i].forEach((value)=>{
                        if(value.spell.indexOf(this.keyWord) > -1 || 
                        value.name.indexOf(this.keyWord) > -1){
                            result.push(value)
                        }
                    })
                }
                this.list = result
            },100)
            
        }
    },
    mounted(){
        const scroll = new BScroll(this.$refs.search)
    }
}
</script>
<style lang='stylus' scoped>
@import '~styles/varibles.styl'
    .search
        height .72rem
        background $bgColor
        padding 0 .1rem
        .search-input 
            box-sizing border-box
            padding 0 .1rem
            width 100%
            height .62rem
            line-height .62rem
            text-align center
            border-radius .05rem
            color #666666
    .search-list
        z-index 1
        overflow hidden
        position absolute   
        top 1.52rem
        left 0
        right 0
        bottom 0
        background #eee
        .search-item
            line-height .62rem
            text-indent .1rem
            background #fff
            border-bottom 1px solid #ccc
</style>
