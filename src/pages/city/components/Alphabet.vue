<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="handelLetterClick"
      @touchstart="handleStart"
      @touchmove="handleMove"
      @touchend="handleEnd"
    >{{item}}</li>
  </ul>
</template>

<script>
import { log } from "util";
import { clearTimeout } from "timers";
export default {
  name: "CityAlphabet",
  props: {
    cities: Object
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    };
  },
  updated() {
    this.startY = this.$refs["A"][0].offsetTop;  // startY值不会变 故保存全局 提升性能1
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
      console.log(e.target.innerText);
      this.$emit("change", e.target.innerText);
    },
    handleStart() {
      this.touchStatus = true;
    },
    handleMove(e) {
      if (this.touchStatus) {
        if (this.timer) {  // 节流操作 提升性能2
          clearTimeout(this.timer);
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 80;
          const index = Math.floor((touchY - this.startY) / 20);
          if (index >= 0 && index < this.letters.length) {
            this.$emit("change", this.letters[index]);
          }
        }, 16);
      }
    },
    handleEnd() {
      this.touchStatus = false;
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