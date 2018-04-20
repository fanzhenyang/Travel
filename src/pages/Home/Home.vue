<template>
  <div class="home">
    <home-header></home-header>
    <home-slide></home-slide>
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
export default {
  data () {
    return {
      imgNum: [1, 2, 3, 4, 5]
    }
  },
  components: {
    HomeHeader,
    HomeSlide,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  }
}
</script>

<style lang="stylus" scoped>

</style>
