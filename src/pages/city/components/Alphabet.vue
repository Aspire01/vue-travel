<template>
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item"
     :ref="item"
     @click="handelLetterClick"
     @touchstart='handleStart'
     @touchmove='handleMove'
     @touchend='handleEnd'
     >
     {{item}}
    </li>
  </ul>
</template>

<script>
import { log } from "util";
export default {
  name: "CityAlphabet",
  props: {
    cities: Object
  },
  data() {
    return {
      touchStatus:false
    };
  },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.cities) {
        letters.push(i);
      }
      return letters;
    }
  },
  methods: {
    handelLetterClick(e) {
      // console.log(e.target.innerText);
      this.$emit("change", e.target.innerText);
    },
    handleStart(){
      this.touchStatus = true
    },
    handleMove(e){
      if(this.touchStatus){
        const startY = this.$refs['A'][0].offsetTop
        const touchY = e.touches[0].clientY - 80 ;
        // console.log(startY);
        const index = Math.floor((touchY - startY) / 20)
        if(index >= 0 && index < this.letters.length){
          this.$emit('change',this.letters[index])
        }
      }
    },
    handleEnd(){
      this.touchStatus = false
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';
@import '~styles/varibles.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
}

.item {
  text-align: center;
  line-height: 0.4rem;
  color: $bgColor;
}
</style>