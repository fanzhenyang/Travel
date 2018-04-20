<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a2/78e4dbcfd45a6d.jpg_r_640x214_7a62b06a.jpg',
          title: '成都必游TOP10',
          desc: '成都的标志，也是现代人对老成都的记忆'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/63/0ffcb5c329a19c.jpg_r_640x214_93fd1e5a.jpg',
          title: '慢游成都最美古镇',
          desc: '撷取一份悠闲，寻觅散落在时光里的幸福'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/e2/2a63e38b84bc8e.jpg_r_640x214_679f0d37.jpg',
          title: '郊野户外深呼吸',
          desc: '做个久违的深呼吸，来一场清肺之旅'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1507/e8/7afdd7b86bf778.jpg_r_640x214_c70adb31.jpg',
          title: '我的周末我做主',
          desc: '在成都Hold各种长假短假'
        }
      ]
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
  padding-bottom: 33.9%
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
