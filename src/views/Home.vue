<template>
  <v-container>
    <v-row>
      <v-col cols="2" :class="$style.list">
        <v-sheet rounded="lg">
          <v-list color="transparent">
            <v-list-item link v-on:click="gaTure">
              <v-list-item-content>
                <v-list-item-title> 遊戲產品</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
           
             <v-list-item link v-on:click="frTure">
              <v-list-item-content>
                <v-list-item-title> 水果產品 </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
           
            <v-list-item link v-on:click="seTure">
              <v-list-item-content>
                <v-list-item-title> 海產產品 </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
         
           
               <v-divider class="my-2"></v-divider>
            <v-list-item link color="grey lighten-4"> </v-list-item>
          </v-list>
        </v-sheet>
      </v-col>

      <v-col cols="10" v-if="seafood">
        <v-sheet min-width="300">
          <Card :data="data[0].commodity" :class="$style.card" />
        </v-sheet>
      </v-col>
      <v-col cols="10" v-if="fruit">
        <v-sheet min-width="200">
          <Card :data="data[1].commodity" :class="$style.card" />
        </v-sheet>
      </v-col>
       <v-col cols="10" v-if="game">
        <v-sheet min-width="200">
          <Card :data="data[2].commodity" :class="$style.card" />
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import Card from "../components/Card.vue";
export default {
  components: {
    Card,
  },
  data() {
    return {
      fruit: false,
      seafood: false,
      game:true,
      data: [
        {
          class: "海產商品",
          commodity: [
            {
              id: 1,
              name: "北海道高級干貝",
              img:"https://www.toro928.com/image/cache/data/1000*1000/20201002072607-600x600.jpg",
              price:"1000",
            },
            {
              id: 2,
              name: "冷凍母香魚",
              img: "https://www.costco.com.tw/medias/sys_master/images/hca/hf9/65992440545310.jpg",
              price: "455",
            },
            {
              id: 3,
              name: "冷凍公香魚",
              img: "https://encrypted-tbn1.gstatic.com/shopping?q=tbn:ANd9GcRSYHNGaN11YhuKAGDUZIayL4rc0S1UJswGU81JezM1e1ouZUmRK1OgnxE4t2SCCzX19uBSbFy7M5Y&usqp=CAc",
              price: "250",
            },
            {
              id: 4,
              name: "冷凍鯛魚片",
              img: "https://s.yimg.com/ob/image/ce720ea7-1807-45b5-9aa6-d80638a35ce7.jpg",
              price: "195",
            },
            {
              id: 5,
              name: "冷凍竹筴魚一夜干",
              img: "https://www.ihergo.com/photo/product/11/300_11_1614673644924.jpg",
              price: "99",
            },
            {
              id: 6,
              name: "冷凍野生生蠔",
              img: "https://d3h1lg3ksw6i6b.cloudfront.net/media/image/2017/04/15/9500ce4a48144d4e80b0f97b1d180d03_Fine+de+Claire.jpg",
              price: "250",
            },
            {
              id: 7,
              name: "大明蝦",
              img: "https://shoplineimg.com/5de5f99b1d0db7003a8db19e/610a3d6dade675003b4b4e1c/2000x.webp?source_format=png",
              price: "2000",
            },
            {
              id: 8,
              name: "邱刀魚",
              img: "https://img.ltn.com.tw/Upload/food/page/2019/05/19/190519-9065-0-ANBro.jpg",
              price: "250",
            },
          ],
        },
        {
          class: "水果商品",
          commodity: [
            {
              id: 1,
              name: "頂級麝香葡萄",
              img: "https://i2.momoshop.com.tw/1632989610/goodsimg/0007/092/192/7092192_R.webp",
              price: "1200",
            },
            {
              id: 2,
              name: "愛妃頂級蘋果",
              img: "https://shopping.line-scdn.net/0hRQoU6WeKDX5SLBucY1VyKQBxEQ86WlRpLRQXXCVpTRp_GUt6PB9ASiN8ABksT0IhOkhFHnR-UUsoHkkgZ01KdnYvBBosT0ogbUNFG34kFk8qTkovbEoW",
              price: "1200",
            },
            {
              id: 3,
              name: "卓蘭新興水果",
              img: "https://img4.momoshop.com.tw/expertimg/0007/891/227/4-1.jpg",
              price: "1100",
            },
            {
              id: 4,
              name: "台東釋迦",
              img: "http://ibw.bwnet.com.tw/image/pool/2014/08/fb22b2d73d92e5760a7a8e9b204cb8f6.jpg",
              price: "800",       
            },
            {
              
              id: 5,
              name: "紐西蘭櫻桃",
              img: "https://cf.shopee.tw/file/c5e986454efe6b4a03857b6a3edacd10",
              price: "2000",       
            
            }
          ],
        },
         {
          class: "遊戲商品",
          commodity: [
            {
              id: 1,
              name: "MyCard 10000虛擬點數卡",
              img: "https://media.etmall.com.tw/nximg/002433/2433207/2433207-1_xxl.jpg?t=18365124091",
              price: "9800",
            },
            {
              id: 2,
              name: "MyCard 5000點虛擬點數卡",
              img: "https://media.etmall.com.tw/nximg/002433/2433206/2433206-1_xxl.jpg?t=18365109496",
              price: "4750",
            },
            {
              id: 3,
              name: "MyCard 3000點虛擬點數卡",
              img: "https://media.etmall.com.tw/nximg/002433/2433205/2433205-1_xxl.jpg?t=18365109497",
              price: "1100",
            },
            {
              id: 4,
              name: "MyCard 500點點數卡",
              img: "https://i3.momoshop.com.tw/1637072184/goodsimg/0005/766/767/5766767_R.webp",
              price: "475",       
            },
            {
              
              id: 5,
              name: "MyCard 150點虛擬點數卡",
              img: "https://media.etmall.com.tw/nximg/002433/2433227/2433227-1_xxl.jpg?t=18365105568",
              price: "143",       
            
            }
          ],
        },
      ],
    };
  },
  mounted() {
    this.data;
  },
  methods: {
    frTure() {
      this.fruit = true;

      if (this.fruit) {
        this.seafood = false;
        this.game =false;
      }
    },
    seTure() {
      this.seafood = true;

      if (this.seafood) {
        this.fruit = false;
        this.game =false;
      }
    },
    gaTure(){
      this.game =true;
      if(this.game){
          this.seafood = false;
          this.fruit = false;
      }
    }
  },
};
</script>
<style module>
/* 在螢幕寬度 768px 以下，就會觸發menu 消失 */

@media (max-width: 768px) {
  .list {
    display: none;
  }
  .card {
    padding: 15px;
    font-size: 20px;
  }
}
</style>