<template>
  <div class="home">
    <home-header></home-header>
    <home-slide></home-slide>
    <div>testasa</div>
  </div>
</template>

<script>
import HomeHeader from '../components/Header'
import HomeSlide from '../components/Slideshow'
export default {
  data () {
    return {
      imgNum: [1, 2, 3, 4, 5]
    }
  },
  components: {
    HomeHeader,
    HomeSlide
  }
}
</script>

<style lang="stylus" scoped>

</style>
