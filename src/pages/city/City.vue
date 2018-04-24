<template>
  <div>
    <home-city></home-city>
    <city-search></city-search>
    <city-list></city-list>
    <city-alphabet></city-alphabet>
  </div>
</template>

<script>
import HomeCity from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/list'
import CityAlphabet from './components/Alphabet'
export default {
  data () {
    return {}
  },
  components: {
    HomeCity,
    CitySearch,
    CityList,
    CityAlphabet
  }
}
</script>

<style lang="stylus" scoped>

</style>
