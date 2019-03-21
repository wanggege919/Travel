<template>
    <div>
        <CityHeader></CityHeader>
        <CitySearch></CitySearch>
        <CityList 
        :hotCities = 'hotCities' 
        :cities = 'cities'
        :letter = 'letter'
        >

        </CityList>
        <CityAlphabet @change = 'handleLetterChange' :cities = 'cities'></CityAlphabet>
    </div>    
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import Axios from 'axios';

export default {
    name: 'City',
    components: {
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    data () {
        return {
           hotCities:[], 
           cities: {},
           letter: ''
        }
    },
    methods:{
        getCityList () {
            Axios.get('/api/city.json')
            .then((res)=>{
                res = res.data
                if(res.ret && res.data){
                    this.hotCities = res.data.hotCities
                    this.cities = res.data.cities
                }
            })
        },
        handleLetterChange(letter){
            this.letter = letter
        }
    },
    mounted () {
        this.getCityList()
    }
}
</script>
<style lang = 'stylus' scoped>
    
</style>
