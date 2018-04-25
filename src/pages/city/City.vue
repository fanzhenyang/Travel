<template>
  <div>
    <home-city></home-city>
    <city-search></city-search>
    <city-list :city="popularCityList" :cities="cities" v-if="popularCityList.length>0"></city-list>
    <city-alphabet :letter="cities"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import HomeCity from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/list'
import CityAlphabet from './components/Alphabet'
export default {
  data () {
    return {
      cities: {},
      popularCityList: []
    }
  },
  components: {
    HomeCity,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      // res得获取
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        console.log(this.cities)
        this.popularCityList = data.hotCities
      }
      // console.log(res)
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
