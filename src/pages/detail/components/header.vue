<template>
  <header>
    <router-link
      tag="div"
      to="/"
      class="header-abs"
      v-show="showAbs"
    >
      <span class="iconfont header-abs-back">&#xe624;</span>
    </router-link>
    <div class="header-flxed"
      v-show="!showAbs"
      :style="opacityStyle"
    >
      <router-link to="/">
        <div class="iconfont header-flxed-back">&#xe624;</div>
      </router-link>
      景点详情
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      // console.log(top)
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () { // 与activated相对应（页面即将被隐藏或者是被替换得时候执行）
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
.header-abs
  position: absolute
  left: .2rem
  top: .2rem
  width: .8rem
  height: .8rem
  line-height: .8rem
  border-radius: .4rem
  text-align: center
  background: rgba(0, 0, 0, .8)
  .header-abs-back
    color: #fff
    font-size: .4rem
.header-flxed
  position: fixed
  top: 0
  left: 0
  right: 0
  height: .86rem
  line-height: .86rem
  text-align: center
  color: #fff
  background: #00bcd4
  font-size: .32rem
  z-index: 20
  .header-flxed-back
    position: absolute
    width: .64rem
    text-align: center
    font-size: .4rem
    top: 0
    left: 0
    color: #fff
</style>
