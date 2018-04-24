<template>
  <header class="c-h">
    城市选择
    <router-link to='/'>
      <div class="iconfont city-back">&#xe624;</div>
    </router-link>
  </header>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
.c-h
  position: relative
  height: .86rem
  line-height: .86rem
  text-align: center
  color: #fff
  background: #00bcd4
  font-size: .32rem
  .city-back
    position: absolute
    width: .64rem
    text-align: center
    font-size: .4rem
    top: 0
    left: 0
    color: #fff
</style>
