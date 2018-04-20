<template>
  <div class="home">
    <home-header></home-header>
    <home-slide :list="swiperList"></home-slide>
    <home-icon></home-icon>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from '../components/Header'
import HomeSlide from '../components/Slideshow'
import HomeIcon from '../components/Icons'
import HomeRecommend from '../components/Recommend'
import HomeWeekend from '../components/Weekend'
import axios from 'axios'
export default {
  data () {
    return {
      city: '',
      swiperList: []
    }
  },
  components: {
    HomeHeader,
    HomeSlide,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(res => {
          this.getHomeInfoSucc(res)
        })
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        console.log(this.swiperList)
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
