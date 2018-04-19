<template>
  <div class="home">
    <home-header></home-header>
    <home-slide></home-slide>
    <home-icon></home-icon>
  </div>
</template>

<script>
import HomeHeader from '../components/Header'
import HomeSlide from '../components/Slideshow'
import HomeIcon from '../components/Icons'
export default {
  data () {
    return {
      imgNum: [1, 2, 3, 4, 5]
    }
  },
  components: {
    HomeHeader,
    HomeSlide,
    HomeIcon
  }
}
</script>

<style lang="stylus" scoped>

</style>
