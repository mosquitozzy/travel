<template>
    <div class="city-header">
        <router-link to="/">
             <span class="city-header-icon iconfont">&#xe624;</span>
        </router-link>
        <h1 class="city-header-title">城市选择</h1>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
 .city-header
  height .68rem
  line-height .68rem
  background #00bcd4
  color #fff
  text-align center
  .city-header-icon
   float left
   left 0
   top 0
   width .8rem
   height .88rem
   line-height .88rem
   font-size .36rem
   color #fff
  .city-header-title
   margin 0 1rem
   line-height .88rem
   font-size .32rem
   ellipsis()
</style>
