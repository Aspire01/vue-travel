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
      spotsList: [
        {
          id: "001",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg",
          keywords: "故宫",
          price: "60"
        },
        {
          id: "002",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_250x250_50c99cf3.jpg",
          keywords: "八达岭长城",
          price: "40"
        },
        {
          id: "003",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_250x250_63e3520a.jpg",
          keywords: "八达岭长城",
          price: "25"
        },
        {
          id: "004",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_250x250_d852635b.jpg",
          keywords: "颐和园",
          price: "38"
        },

        {
          id: "005",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/201405/12/51b63883c25f5d87af3c08bb016e2bd7.jpg_250x250_6ec2f798.jpg",
          keywords: "恭王府",
          price: "58"
        },
        {
          id: "006",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1602/92/920e47352552c1c990.water.jpg_250x250_ee99c18e.jpg",
          keywords: "天坛公园",
          price: "40"
        },

        {
          id: "007",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1501/40/40b2b6c951b28fdd.water.jpg_250x250_ecfa0df2.jpg",
          keywords: "水立方",
          price: "248"
        },

        {
          id: "008",
          imgUrl:
            "https://imgs.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_250x250_3588bc9a.jpg",
          keywords: "北京世界博览会",
          price: "123"
        }
      ]
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