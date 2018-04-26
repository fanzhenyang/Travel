<template>
  <div class="home">
    <home-header></home-header>
    <home-slide :list="swiperList" v-if="swiperList.length>0"></home-slide>
    <home-icon :list="iconList" v-if="iconList.length>0"></home-icon>
    <home-recommend :list="recommendList" v-if="recommendList.length>0"></home-recommend>
    <home-weekend :list="weekendList" v-if="weekendList.length>0"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSlide from './components/Slideshow'
import HomeIcon from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  components: {
    HomeHeader,
    HomeSlide,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  mounted () {
    this.getHomeInfo()
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
      console.log(res)
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
