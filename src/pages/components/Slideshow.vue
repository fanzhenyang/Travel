<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img :src="item.imgUrl" class="swiper-img" />
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  props: {
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/14/21f410d1016c8702.jpg_640x200_84d0effe.jpg'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/58/f55d3bc7fe9cd502.jpg_640x200_4153eac0.jpg'
        }
      ]
    }
  },
  methods: {
  },
  created: function () {
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff !important
.wrapper
  width: 100%
  height: 0
  overflow: hidden
  padding-bottom: 31.25%
  background: #eee 
  .swiper-img
    width: 100%
</style>
