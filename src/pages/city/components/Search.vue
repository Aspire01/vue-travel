<template>
  <div>
    <div class="search-wrapper">
    <input type="text" v-model='keyword' class="search-input" placeholder="输入城市名或拼音">
  </div>
  <div class="search-content" ref="search" v-show="keyword">
    <ul>
      <li v-for="item of list" :key='item.id' class="search-item">{{item.name}}</li>
      <li class="search-item" v-show="!hasNoData">没有找到匹配项</li>
    </ul>
  </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
export default {
  name: 'CitySearch',
  props:{
    cities: Object
  },
  data() {
    return {
      keyword:'',
      list:[],
      timer:null
    }
  },
  computed:{
    hasNoData(){
      return this.list.length
    }
  },
  watch:{
    keyword(){
      if(this.timer){
        clearTimeout(this.timer)
      }
      if(!this.keyword){
        this.list = []
        return
      }
      this.timer = setTimeout(()=> {
        const arr = []
        for (let i in this.cities){
          this.cities[i].forEach((value)=>{
            if (value.spell.indexOf(this.keyword) != -1 || value.name.indexOf(this.keyword) != -1){
              arr.push(value)
            }
          })
        }
        this.list = arr
      },100)
    }
  },
  mounted(){
    this.scroll = new Bscroll(this.$refs.search);
  }
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
  .search-content
    position absolute
    overflow hidden
    top 1.58rem
    left 0
    right 0
    bottom 0
    background #eee
    z-index 1
    .search-item 
      line-height .62rem
      padding-left .2rem
      color #666
      background #fff
</style>