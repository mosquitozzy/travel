<template>
    <div class="detail-base-info">
        <div class="info-card">
            <div class="info-comment">
                <div class="info-comment-top">
                    <span class="comment-score">5.0</span>
                    <span class="comment-text">分</span>
                    <span class="comment-desc">超赞</span>
                </div>
                <div class="info-comment-bottom">
                    <span class="comment-total">25560条评论</span>
                    <span class="comment-total">3条攻略</span>
                    <span class="iconfont comment-total-rightarrow">&#xe61c;</span>
                </div>
            </div>
            <div class="info-introduce">
                <div class="info-introduce-top">景点简介</div>
                <div class="info-introduce-bottom">开放时间、贴士</div>
                <div class="iconfont info-introduce-bottom-rightarrow">&#xe61c;</div>
            </div>
        </div>
        <div class="info-address">
            <span class="iconfont info-address-icon">&#xe613;</span>
            <p class="info-address-text">广东省深圳市南山区</p>
            <span class="iconfont info-address-rightarrow">&#xe61c;</span>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailBaseInfo'
}
</script>

<style lang="stylus" scoped>
 .detail-base-info
   position relative
   top: -.1rem;
   padding: .1rem .2rem 0 .2rem;
   margin-bottom: .1rem;
   background: #fff;
   border-radius .1rem .1rem 0 0

   .info-card
     padding-top: .1rem;
     padding-bottom: .2rem;
     overflow hidden

     .info-comment
       float left
       position relative
       width 50%
       display block

       .comment-score
         font-size: .44rem
         color: #ff8300
         line-height: .44rem

       .comment-text
         font-size: .28rem
         color: #ff8300
         line-height: .48rem

       .comment-desc
         font-size: .28rem
         color: #ff8300
         line-height: .48rem
         margin-left .2rem

       .comment-total
         font-size: .24rem
         color: #9e9e9e
         line-height: .32rem
         margin-right: .2rem

       .comment-total-rightarrow
         position: absolute;
         top: .3rem;
         right: .2rem;
         color: #9e9e9e;
         font-size: .24rem;

     .info-introduce
       float right
       position relative
       right 0
       width 50%

       .info-introduce-top
         font-size: .28rem;
         color: #212121;
         line-height: .48rem;
         padding-left: .3rem;

       .info-introduce-bottom
         color: #9e9e9e;
         font-size: .24rem;
         padding-left: .3rem;

       .info-introduce-bottom-rightarrow
         position: absolute;
         top: .3rem;
         right: .2rem;
         color: #9e9e9e;
         font-size: .24rem;

   .info-address
     display block
     position relative
     padding .2rem 0
     line-height .36rem
     color #212121

     .info-address-icon
       position absolute
       left 0
     .info-address-text
       padding-left .56rem
     .info-address-rightarrow
       position: absolute
       right: 0
       top: 50%
       margin-top: -.14rem
       color: #9e9e9e
       font-size: .24rem

</style>
