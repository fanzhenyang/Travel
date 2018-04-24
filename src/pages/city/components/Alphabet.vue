<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
.list
  position: absolute
  display: flex
  flex-direction: column
  justify-content: center
  top: 1.58rem
  right: 0
  bottom: 0
  width: .4rem
  .item
    text-align: center
    line-height: .4rem
    color: #00bcd4
</style>