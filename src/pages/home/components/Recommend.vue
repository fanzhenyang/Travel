<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link
        :to="'/detail/' + item.id"
        tag="li" class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id"
      >
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
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
  margin-top: .2rem
.item
  display: flex
  height: 1.9rem
  overflow: hidden
  .item-img
    width: 1.7rem
    heigh: 1.7rem
    padding: .1rem
  .item-info
    flex: 1
    padding: .1rem
    min-width: 0
    .item-title
      line-height: .54rem
      font-size: .32rem
    .item-desc
      line-height: .4rem
      color: #898989
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
    .item-button
      background: #ff9300
      padding: 0 .1rem
      border-radius: .06rem
      margin-top: .12rem
      color: #fff
      line-height: .44rem

</style>
