<template>
  <div class="header-wrapper">
    <div class="header-title">城市选择</div>
    <router-link to="/">
      <div class="back-wrap">
        <span class="iconfont">&#xe60c;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader',
  data() {
    return {
      
    }
  },
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  @import '~styles/varibles.styl';
  a
    color #fff
  .header-wrapper
    position relative
    background #00BCD4
    height $headerHeight
    line-height $headerHeight
    .header-title
      width 3rem
      margin 0 auto 
      font-size .36rem
      text-align center
      color #fff
      ellipsis()
    .back-wrap
      position absolute
      width $headerHeight
      height $headerHeight
      left 0
      top 0
      line-height $headerHeight
      text-align center
      color #fff
</style>