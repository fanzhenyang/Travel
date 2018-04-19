<template>
  <div class="home">
    <home-header></home-header>
    <home-slide></home-slide>
    <home-icon></home-icon>
    <home-recommend></home-recommend>
  </div>
</template>

<script>
import HomeHeader from '../components/Header'
import HomeSlide from '../components/Slideshow'
import HomeIcon from '../components/Icons'
import HomeRecommend from '../components/Recommend'
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
    HomeRecommend
  }
}
</script>

<style lang="stylus" scoped>

</style>
