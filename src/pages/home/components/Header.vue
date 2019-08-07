<<template>
    <div class='header'>
     <div class='header-left'>
         <span class='iconfont'>&#xe60c;</span>
     </div>
     <div class='header-input'>
          <span class='iconfont'>&#xe600;</span>
         输入景点/游玩主题
     </div>
     <div class='header-right'>
         城市
          <span class='iconfont'>&#xe601;</span>
     </div>
    </div>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    .header
        background :$bgColor
        display :flex
        height :.86rem
        line-height :.86rem
        color #fff
        .header-left
            width : .64rem
            float  : left
            display flex
            justify-content center
        .header-right 
            float : right
            width 1.24rem
            text-align center
        .header-input
            flex :1
            background #fff
            border-radius .1rem
            height .64rem
            margin-top .11rem
            line-height .64rem
            margin-left .2rem
            color #ccc
            padding 0 .2rem
</style>