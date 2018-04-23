<template>
  <header class="h-main">
    <!--左边开始-->
    <div class="h-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <!--中间输入框-->
    <div class="h-cont">
      <span class="iconfont">&#xe632;</span>
      搜索旅行地/酒店/景点
    </div>
    <!--右边城市列表-->
    <div class="h-right">
      城市
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </header>
</template>

<script>
export default {
  props: {
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
.h-main
  display: flex
  justify-content: space-between
  line-height: .86rem
  background: #00bcd4
  .h-left
    width: .64rem
    .back-icon
      color: #fff
      text-align: center
      font-size: .4rem
  .h-cont
    position: relative
    height: .64rem
    line-height: .64rem
    margin-top: .12rem
    margin-left: .2rem
    margin-right: .2rem;
    padding-left: .2rem
    border-radius: .1rem
    flex: 1
    color: #ccc
    background: #fff
  .h-right
    width: 1.24rem
    color: #fff
    .arrow-icon
      margin-left: -.04rem
      font-size: .24rem
</style>
