<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of page" :key='index'>
        <ul class="li-wrap">
          <li class="item" v-for="item of page" :key="item.id">
            <div class="img-wrap">
              <img :src="item.imgUrl" />
            </div>
            <p class="item-keywords">{{item.keywords}}</p>
            <p />
          </li>
        </ul>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
import { constants } from "fs";
import { log } from "util";
export default {
  name: "HomeIcons",
   props: {
    iconsList: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: false // 实现循环轮播
      },
    };
  },
  computed: {
    page() {
      let _list = this.iconsList
      let pages = []
      _list.forEach((item, index) => {
        let page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item);
      });
      return pages
    }
  }
};
</script>

<style lang="stylus" scoped>
// 实现宽高比2:1的盒子 这是什么原理？
.icons {
  position: relative;
  padding-top: 0.1rem;

  .li-wrap {
    width: 100%;
    display: flex;
    flex-wrap: wrap;

    .item {
      width: 25%;
      height: auto;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding-top: 0.1rem;

      .img-wrap {
        width: 1.1rem;
        height: 1.1rem;

        > img {
          width: 100%;
          height: 100%;
        }
      }

      .item-keywords {
        font-size: 0.28rem;
        color: #212121;
        margin-top: 0.1rem;
      }
    }
  }
}
</style>