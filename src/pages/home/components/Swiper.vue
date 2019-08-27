<template>
  <div class="swiper-wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img :src="item.imgUrl" alt />
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
    swiperList: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true // 实现循环轮播
      },
    };
  }
};
</script>

<style lang="stylus" scoped>>>> .swiper-pagination-bullet-active {
  background: #fff;
}

.swiper-wrapper {
  height: 200px;
}
</style>