<template>
    <div>
        <h2 class="weekend-title">周末去哪儿</h2>
        <div class="weekend-item" v-for="item of list" :key="item.id">
            <div class="weekend-item-img-container">
                <img class="weekend-item-img" :src="item.imgSrc">
            </div>
            <div class="weekend-item-info">
                <p class="weekend-item-name">{{item.weekendItemName}}</p>
                <p class="weekend-item-desc">{{item.weekendItemDesc}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scope>
@import '~styles/mixins.styl'
.weekend-title
 height .8rem
 padding-left .26rem
 line-height .8rem
 color #212121
 background #eee
.weekend-item
 display block
 height 100%
 width 100%
 .weekend-item-img-container
  overflow hidden
  height 0
  padding-bottom 37.4375%
  .weekend-item-img
   width 100%
 .weekend-item-info
  position relative
  padding .14rem .2rem .2rem .2rem
  .weekend-item-name
   padding-right 1.4rem
   color #212121
   font-size .28rem
   line-height .48rem
   ellipsis()
  .weekend-item-desc
   padding-right 1.4rem
   color #616161
   font-size .24rem
   line-height .42rem
   ellipsis()
</style>
