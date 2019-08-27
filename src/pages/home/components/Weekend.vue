<template>
  <div class="weekend-wrapper">
    <div class="slicer"></div>
    <div class="w-title-wrap">
      <div class="left">
        <img src="https://imgs.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt />
        <span>本周热门榜单</span>
      </div>
      <div class="right">
        <span>全部榜单</span>
        <span>
          <i class="iconfont">&#xe60a;</i>
        </span>
      </div>
    </div>
    <div class="travel-spot-wrapper">
      <ul class="li-wrap">
        <swiper :options="swiperOption">
          <swiper-slide v-for="item of spotsList" :key="item.id">
            <li class="spot-item">
              <div class="spot-item-img-wrap">
                <img :src="item.imgUrl" alt />
              </div>
              <p class="spot-keywords">{{item.keywords}}</p>
              <div class="spot-price">
                <span class="p-1">￥</span>
                <span class="p-2">{{item.price}}</span>
                <span class="p-3">起</span>
              </div>
            </li>
          </swiper-slide>
          <div class="swiper-scrollbar" slot="scrollbar"></div>
        </swiper>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props: {
    spotsList: Array
  },
  data() {
    return {
      swiperOption: {
        el: ".swiper-scrollbar",
        grabCursor: true,
        slidesPerView: "auto", // 不加这个属性的时候 是无限长
        mousewheelControl: false, // 能够是的鼠标滚动控制滚动
        freeMode: true,
        hide: true,

        // watchSlidesVisibility: true,
        // watchSlidesProgress: true,
        // spaceBetween: 2 //设置两个swiper-slide之间的距离
      },
    };
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

>>>.swiper-slide {
  width: 2rem !important;
  margin-left: 0.2rem;
}

>>>.swiper-slide:nth-child(1) {
  margin-left: 0;
}

.weekend-wrapper {
  background: #fff;
}

.slicer {
  height: 0.2rem;
  background: #f5f5f5;
}

.w-title-wrap {
  display: flex;
  padding: 0.24rem 0.24rem 0.26rem;
  justify-content: space-between;
  align-items: center;

  .left {
    display: flex;
    align-items: center;

    img {
      width: 0.3rem;
      height: 0.3rem;
      vertical-align: middle;
    }

    span {
      font-size: 0.32rem;
      margin-left: 0.1rem;
    }
  }

  .right {
    display: flex;
    align-items: center;

    span {
      font-size: 0.24rem;
      color: #616161;
    }
  }
}

.travel-spot-wrapper {
  padding: 0.2rem 0.2rem;

  .li-wrap {
    display: flex;
  }

  .spot-item:nth-child(1) {
    margin-left: 0;
  }

  .spot-item {
    margin-left: 0.2rem;

    .spot-keywords {
      font-size: 0.24rem;
      text-align: center;
      margin-top: 0.1rem;
      ellipsis();
      margin-bottom: 0.1rem;
    }

    .spot-price {
      display: flex;
      justify-content: center;
      align-items: center;

      .p-1 {
        color: #ff8300;
        font-size: 0.2rem;
      }

      .p-2 {
        color: #ff8300;
        font-size: 0.24rem;
      }
    }

    .spot-item-img-wrap {
      width: 2rem;
      height: 2rem;

      > img {
        width: 100%;
        height: 100%;
      }
    }

    width: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>