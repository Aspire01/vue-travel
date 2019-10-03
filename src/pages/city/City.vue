<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities='cities' :hot='hotCityies'></city-list>
    <city-alphabet :cities='cities'></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header';
import CitySearch from './components/Search';
import CityList from './components/List';
import CityAlphabet from './components/Alphabet';
import { log } from 'util';
export default {
  name: "City",
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods:{
      getCityInfo(){
        axios.get('/api/city.json')
          .then(this.handleSuccess)
      },
      handleSuccess(res){
        console.log(res)
        res = res.data
        if(res.ret && res.data){
          const data = res.data
          this.cities = data.cities
          this.hotCityies = data.hotCityies
        }
      }
  },
  mounted(){
    this.getCityInfo();
  },
  data() {
    return {
      cities:{},
      hotCityies:[]
    };
  }
};
</script>

<style lang="stylus" scoped></style>