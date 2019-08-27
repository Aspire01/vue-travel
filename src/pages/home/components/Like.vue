<template>
  <div class="like-wrapper">
    <div class="slicer"></div>
    <div class="like-list-wrap">
      <div class="title">
        <img src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png">
        <span class="guess">猜你喜欢</span>
      </div>
      <div class="item-wrap" v-for="item of likesList" :key='item.id'>
        <div class="spot-box">
          <img :src="item.img_url">
        </div>
        <div class="spot-desc-box">
          <p class="name">{{item.spot_name}}</p>
          <p class="comments">{{item.comments_num}}条评论</p>
          <p class="price-and-location">
            <span><span class="price">￥<span class="num">{{item.price}}</span></span>起</span>
            <span>{{item.location}}</span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'HomeLike',
  props: {
    likesList: Array
  },
  data() {
    return {
    }
  },
}

</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .like-wrapper
    .slicer
      width 100%
      height .2rem
      background #F5F5F5
    .like-list-wrap
      .title
        padding .24rem 0 .26rem
        > img 
          width .3rem
          height .3rem
          vertical-align middle
          margin-left .24rem
        .guess
          font-size .32rem
          margin-left .1rem
      .item-wrap
        display flex
        padding .24rem .24rem .26rem
        .spot-box
          flex 0 0 2rem
          > img 
            width 100%
            height 100%
        .spot-desc-box 
          flex 1
          display flex
          flex-direction column
          padding .3rem 0 .26rem .2rem
          justify-content space-between
          min-width 0
          .name 
            font-size .32rem
            color #212121
            ellipsis()
          .comments
            font-size .24rem
            color #616161
            ellipsis()
          .price-and-location
            display flex
            justify-content space-between
            align-items center
            .price
              color #FF9A2F
              font-size .24rem
              .num 
                font-size .32rem
</style>