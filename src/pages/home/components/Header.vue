<<template>
    <div class='header'>
     <div class='header-left'>
         <span class='iconfont'>&#xe60c;</span>
     </div>
     <div class='header-input'>
          <span class='iconfont'>&#xe600;</span>
         输入景点/游玩主题
     </div>
     <router-link to='/city'>
        <div class='header-right'>
          {{this.city}}
          <span class='iconfont'>&#xe601;</span>
        </div>
     </router-link>
    </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
    name:'Header',
    computed: {
        ...mapState(['city'])  // vuex提供的用于将数据映射到city中
    }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    a
        color #fff
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
            min-width 1.24rem
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