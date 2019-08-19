<<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-weekend></home-weekend>
        <home-like></home-like>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icon'
import HomeWeekend from './components/Weekend'
import HomeLike from './components/Like'
import axios from 'axios'
export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeWeekend,
        HomeLike
    },
    methods: {
        getHomeInfo () {
            // 路径使用代理实现转发
            axios.get('/static/mock/index.json')
                .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc (res) {
            console.log(res)
        },
    },
    mounted () {
        this.getHomeInfo();
    }
}
</script>

<style lang="">
    
</style>