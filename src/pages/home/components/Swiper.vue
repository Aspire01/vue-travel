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
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true // 实现循环轮播
      },
      swiperList: [
        {
          id: "01",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/a4c27b0a5fc1d9e9e620225869089b12.jpg_750x200_e4720428.jpg"
        },
        {
          id: "02",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/0b0622e5b6ac5fbed3084dd2832e6f8f.jpg_750x200_895321b6.jpg"
        },
        {
          id: "03",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20198/ffb06b600df4c655d10a1dfef4a8d0e9.jpg_750x200_7b1aec5e.jpg"
        }
      ]
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