<template>
    <div class="city-list" ref="wrapper">
      <div>
        <div class="area">
             <h2 class="title border-topbottom">热门城市</h2>
             <ul class="city-popular-list">
              <li class="city-popular-item"  v-for="item of hotCities" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
             </ul>
        </div>
        <div class="area">
            <h2 class="title border-topbottom">字母排序</h2>
            <ul class="character-list">
                <li v-for="(item, key) of cities" :key="key" @click="handleLetterClick">{{key}}</li>
            </ul>
        </div>
        <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
            <h2 class="title border-topbottom">{{key}}</h2>
            <ul class="city-character-list">
              <li class="city-character-item" v-for="innerItem of item" :key="innerItem.id" @click="handleCityClick(innerItem.name)">{{innerItem.name}}</li>
            </ul>
        </div>
      </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
import {mapMutations} from 'vuex'
export default {
  name: 'CityList',
  data () {
    return {
      character: this.letter
    }
  },

  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },

  watch: {
    character () {
      if (this.character) {
        const element = this.$refs[this.character][0]
        this.scroll.scrollToElement(element)
      }
    },
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  methods: {
    handleLetterClick (e) {
      if (e.target.innerText) {
        this.character = this.letter
        this.character = e.target.innerText
      }
    },
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity']) // 将store mutations.js中的changeCity方法映射到list组件中changeCity方法，可以直接调用
  },

  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper, {click: true})
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.city-list
 position absolute
 overflow hidden
 top 1.58rem
 left 0
 right 0
 bottom 0
 .border-topbottom
  &:before
   border-color #ccc
  &:after
   border-color #ccc

 .title
  line-height .44rem
  background #eee
  padding-left .2rem
  color #666
  font-size .26rem
 .city-popular-list
  padding .1rem .6rem .1rem .1rem
  overflow hidden //子元素浮动导致父元素高度塌陷，需要使用overflow hidden清除浮动
  .city-popular-item
    float left
    width 33.33%
    line-height .9rem
    padding .1rem 0
    text-align center
    ellipsis()

 .character-list
  padding .1rem .6rem .1rem .1rem
  overflow hidden
  li
    float left
    width 16.66%
    line-height .7rem
    padding .1rem 0
    text-align center
    ellipsis()

 .city-character-list
   padding .1rem .6rem .1rem .1rem
   overflow hidden
   .city-character-item
    float left
    width 25%
    line-height .7rem
    padding .1rem 0
    text-align center
    ellipsis()

</style>
