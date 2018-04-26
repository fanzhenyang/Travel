<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">
              <!-- {{this.$store.state.city}} -->
              {{this.currentCity}}
              </div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
            v-for="cityItem of popularCityList"
            :key="cityItem.id"
            @click="handleCityClick(cityItem.name)"
          >
            <div class="button">{{cityItem.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
          {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  props: {
    city: {
      type: [Array]
    },
    cities: {
      type: [Object]
    },
    letter: {
      type: [String]
    }
  },
  data () {
    return {
      popularCityList: this.city
    }
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper) // 引用了插件达到原生APP效果滚动
  },
  watch: { // 监听器
    letter () {
      if (this.letter) {
        // element获取到是一个数组,取第一个
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  methods: {
    handleCityClick (city) {
      // this.$store.dispatch('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>

<style lang="stylus" scoped>
.border-topbottom
  &:before
    border-color: #ccc
  &:after
    border-color: #ccc
.border-topbottom
  &:before
    border-color: #ccc
.list
  position: absolute
  overflow: hidden
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
.title
  line-height: .54rem
  background: #eee
  padding-left: .2rem
  color: #666
  font-size: .24rem
.button-list
  overflow: hidden
  padding: .1rem .6rem .1rem .1rem
  .button-wrapper
    width: 33.33%
    float: left
    .button
      padding: .1rem 0
      text-align: center
      margin: .1rem
      border: .02rem solid #ccc
      border-radius: .06rem
.item-list
  .item
    line-height: .76rem
    padding-left: .2rem
</style>
