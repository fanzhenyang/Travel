<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
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
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1712/5d/5d4f18e64813d0f6a3.img.jpg_200x200_2a260ea1.jpg',
          title: '欢乐谷',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1704/a5/a59677101e07d38a3.img.jpg_200x200_6064e939.jpg',
          title: '国色天乡·陆地乐园',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201309/24/977fea7b3c5cd758c8d65eac.jpg_200x200_697c3b3f.jpg',
          title: '欢成都熊猫基地乐谷',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_200x200_63285bd9.jpg',
          title: '成都海昌极地海洋公园',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201407/03/a584374ee80b738e2600d6bcaf1299e3.jpg_200x200_c26fb243.jpg',
          title: '都江堰',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/b0/b0132e78efa00572.water.jpg_200x200_3f499a59.jpg',
          title: '青城山',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0007',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/16/ae96ce4058bd5cf093835fbb.jpg_200x200_e4cb9743.jpg',
          title: '青城道温泉',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0008',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/5d/5dab68ebb296bbd5a3.img.png_200x200_1181e5bc.png',
          title: '漫花庄园',
          desc: '刺激、冒险、探险'
        },
        {
          id: '0009',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/c4/c4b6c51a2ac942cfa3.img.jpg_200x200_2805e881.jpg',
          title: '花舞人间',
          desc: '刺激、冒险、探险'
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
