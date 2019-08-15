<<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-weekend></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icon'
import HomeWeekend from './components/Weekend'
export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeWeekend
    }
}
</script>

<style lang="">
    
</style>