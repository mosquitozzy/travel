<template>
   <div>
      <div class="recommend-title">热销推荐</div>
      <ul>
        <router-link class="recommend-item" v-for="item of list" :key="item.id" :to="'/detail/' + item.id">
          <div class="item-img-wrapper">
            <img class="item-img" :src="item.imgSrc" >
          </div>
          <div class="item-info">
            <div class="item-info-title">{{item.itemInfoTitle}}</div>
            <div class="item-info-comment"><span class="item-info-comment-star">★★★★★</span><span class="item-info-comment-content">{{item.itemInfoComment}}</span></div>
            <div class="item-info-price"><span class="item-info-price-symbol">￥</span><em class="item-info-price-num">{{item.itemInfoPrice}}</em>起<span class="item-info-price-region">{{item.itemInfoRegion}}</span></div>
          </div>
        </router-link>
      </ul>
      <div class="recommend-all">查看所有产品</div>
   </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scope>
@import '~styles/mixins.styl'
 .recommend-title
  margin-top .2rem
  line-height .8rem
  background: #eee
  text-indent .2rem
 .recommend-item
  display flex
  height 2.4rem
  .item-img
   width 2.1rem
   height 2.1rem
   padding .15rem
  .item-info
   width 4.8rem
   height 2.1rem
   padding .15rem
   .item-info-title
    margin-top .26rem
    height .44rem
    line-height .44rem
    font-size .32rem
    color #212121
    ellipsis()
   .item-info-comment
    margin-top .14rem
    height .34rem
    .item-info-comment-star
     z-index 2
     color #ffb436
    .item-info-comment-content
     padding-left .24rem
     color #616161
     font-size .24rem
     line-height .34rem
     vertical-align text-bottom
   .item-info-price
    margin-top .22rem
    color #616161
    font-size .24rem
    line-height .4rem
    .item-info-price-symbol
     color #ff8300
    .item-info-price-num
     font-size .4rem
     color #ff8300
    .item-info-price-region
     float right
     padding-right .4rem
 .recommend-all
  margin-top .2rem
  line-height .8rem
  border-top solid .01rem #eee
  text-indent .2rem
  text-align center
  color #00afc7
</style>
