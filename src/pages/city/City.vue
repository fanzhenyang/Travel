<template>
  <div>
    <home-city></home-city>
    <city-search :cities="cities"></city-search>
    <city-list :letter="letter" :city="popularCityList" :cities="cities" v-if="popularCityList.length>0"></city-list>
    <city-alphabet :letter="cities" @change="handleLetterChage"></city-alphabet>
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
      popularCityList: [],
      letter: ''
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
        this.popularCityList = data.hotCities
      }
    },
    handleLetterChage (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
