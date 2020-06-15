<template>
    <div class="detail-banner-wrap">
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" :src="bannerImg" alt="">
            <div class="banner-info">
                <p class="banner-info-title">{{this.sightName}}</p>
            </div>
            <div class="banner-icon">
                <span class="iconfont icon-img">&#xe61b;</span>
                <em class="banner-icon-font">{{this.bannerImgs.length}}</em>
            </div>
        </div>
        <fade-animation>
            <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
        </fade-animation>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner::after
    content '\0020'
    position absolute
    bottom 0
    left 0
    width 100%
    min-height .6rem
    background-color transparent
    background-image linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,.8))
  .banner
   position relative
   overflow hidden
   height 0
   padding-bottom 55%
   .banner-img
    width 100%
   .banner-info
    position absolute
    left .2rem
    right .2rem
    bottom .26rem
    min-height .4rem
    color #fff
    font-size .36rem
   .banner-icon
    display flex
    font-size .24rem
    position absolute
    left .2rem
    bottom .86rem
    color #fff
    .icon-img
      font-size .24rem
    .banner-icon-font
      margin-left .1rem

</style>
