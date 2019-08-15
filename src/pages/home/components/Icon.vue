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
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: false // 实现循环轮播
      },
      iconsList: [
        {
          id: "001",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          keywords: "景点门票"
        },
        {
          id: "002",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/f0f00d6dfe038c044dbc9a437f58b0eb.png",
          keywords: "一日行"
        },
        {
          id: "003",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/437aad2dd0c1edb38fee0c51f8f9dd02.png",
          keywords: "热门演出"
        },
        {
          id: "004",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/d0d101c23a73467de740ecf68602cd17.png",
          keywords: "壶口瀑布"
        },
        {
          id: "005",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          keywords: "大明宫"
        },
        {
          id: "006",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png",
          keywords: "动植物园"
        },
        {
          id: "007",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png",
          keywords: "华清宫"
        },
        {
          id: "008",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png",
          keywords: "兵马俑"
        },
           {
          id: "009",
          imgUrl:
            "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/9c76635f623759e3db287c4850fcb0a5.png",
          keywords: "华山"
        },
           {
          id: "010",
          imgUrl:
            "https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png",
          keywords: "博物馆"
        },
      ]
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