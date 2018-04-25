<template>
  <ul class="list">
    <li class="item" v-for="(item, key) of letter" :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
  props: {
    letter: {
      type: [Object]
    }
  },
  data () {
    return {
      letterList: this.letter
    }
  },
  mounted () {
    console.log(this.letter)
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
