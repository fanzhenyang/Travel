<template>
  <div>
    <home-city></home-city>
    <city-search></city-search>
  </div>
</template>

<script>
import HomeCity from './components/Header'
import CitySearch from './components/Search'
export default {
  data () {
    return {}
  },
  components: {
    HomeCity,
    CitySearch
  }
}
</script>

<style lang="stylus" scoped>

</style>
