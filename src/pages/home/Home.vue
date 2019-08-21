<<template>
    <div>
        <home-header :city="city"></home-header>
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
import { log } from 'util';
import { constants } from 'fs';
export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeWeekend,
        HomeLike
    },
    data () {
        return {
            city: ''
        }
    },
    methods: {
        getHomeInfo () {
            // 路径使用代理实现转发
            axios.get('/api/index.json')
                .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc (res) {
            console.log(res)
            res = res.data;
            if(res.ret && res.data){
                let data = res.data
                this.ctiy = data.city
            }
        },
    },
    mounted () {
        this.getHomeInfo();
    }
}
</script>

<style lang="">
    
</style>