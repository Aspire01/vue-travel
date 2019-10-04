<<template>
    <div>
        <home-header></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :iconsList="iconsList"></home-icons>
        <home-weekend :spotsList="spotsList"></home-weekend>
        <home-like :likesList="likesList"></home-like>
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
import { constants, truncate } from 'fs';
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
            swiperList:[],
            iconsList: [],
            spotsList: [],
            likesList: []
        }
    },
    methods: {
        getHomeInfo () {
            // 路径使用代理实现转发
            axios.get('/api/index.json')
                .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc (res) {
            // console.log(res)
            res = res.data;
            if(res.ret && res.data){
                let data = res.data
                this.swiperList = data.swiperList
                this.iconsList = data.iconsList
                this.spotsList = data.spotsList
                this.likesList = data.likesList
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