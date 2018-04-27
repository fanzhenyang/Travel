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
import { mapState } from 'vuex'
export default {
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      lastCity: ''
    }
  },
  components: {
    HomeHeader,
    HomeSlide,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city)
        .then(res => {
          this.getHomeInfoSucc(res)
        })
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
    this.lastCity = this.city
  },
  // 使用keep-alive，vue会自动增加一个钩子函数activated
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
