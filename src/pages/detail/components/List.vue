<template>
    <div class="content-list">
        <div class="item" v-for="(item, index) of list" :key="index">
            <div class="item-title border-bottom">
                <span class="item-title-icon"></span>
                {{item.title}}
            </div>
            <div v-if="item.children" class="item-children">
                <detail-list :list="item.children"></detail-list>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    font-weight bold
  .item-children
    padding 0 .1rem
    font-weight 300
</style>
