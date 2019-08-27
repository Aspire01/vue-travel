<template>
  <div class="search-wrapper">
    <input type="text" class="search-input" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
  data() {
    return {
      
    }
  },
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  @import '~styles/varibles.styl';
  .search-wrapper
    height .72rem
    line-height .72rem
    background #00BCD4
    padding 0 .1rem
    .search-input
      width 100%
      height .62rem
      line-height .62rem
      text-align center
      padding 0 .1rem
      box-sizing border-box
      border-radius .06rem
      color #666
</style>