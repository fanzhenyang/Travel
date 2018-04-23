<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: [Array, Object]
    }
  },
  data () {
    return {
      recommendList: this.list
    }
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height: .8rem
  text-indent: .2rem
  background: #ccc
.item-img-wrapper
  height: 0
  overflow: hidden
  padding-bottom: 37.09%
  .item-img
    width: 100%
.item-info
  padding: .1rem
  .item-title
    line-height: .54rem
    font-size: .32rem
  .item-desc
    line-height: .4rem
    color: #898989
    overflow: hidden
    white-space: nowrap
    text-overflow: ellipsis

</style>
