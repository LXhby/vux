<template>
    <div class="wechat">
      <!--轮播图-->
      <swiper auto loop @on-index-change="onSwiperItemIndexChange" v-model="swiperItemIndex" dots-position="center" height="200px">
        <swiper-item class="swiper-demo-img" v-for="(item, index) in picList" :key="index">
          <img :src="item">
        </swiper-item>
      </swiper>
      <!--<swiper loop auto :list="picList" :index="demo06_index" @on-index-change="demo06_onIndexChange" loop></swiper>-->
      <!--轮播图-->



      <!--九宫格
        label:名字
        link:路由--name
      -->
      <grid :show-lr-borders="false">
        <grid-item :label="item.pickname" v-for="(item,index) in grid" :key="index" :link="item.name">
          <img slot="icon" :src="item.src">
        </grid-item>
      </grid>
      <!--九宫格-->

    </div>
</template>

<script>
  import { Grid, GridItem ,SwiperItem,Swiper} from 'vux'
    export default {
      name: "wechat",
      components:{
          Grid,
          GridItem,
          Swiper,
          SwiperItem
      },
      data(){
        return{
          grid:[
            {
              pickname:'天气预报',
              name:'weather',
              src:require('../../assets/images/tianqi.png')
            },
            {
              pickname:'图文列表',
              name:'picture',
              src:require('../../assets/images/pic.png')
            },
            {
              pickname:'快递查询',
              name:'kuaidi',
              src:require('../../assets/images/kuaidi.png')
            },
            {
              pickname:'火车票查询',
              name:'huoche',
              src:require('../../assets/images/huoche.png')
            }

          ],
          picList:[
            "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=101312452,3605106964&fm=26&gp=0.jpg",
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1540369945921&di=fe604397e4bc44415018ee9ae5825361&imgtype=0&src=http%3A%2F%2Fimages6.fanpop.com%2Fimage%2Fphotos%2F34100000%2FOne-P13c3-one-piece-34104387-1366-768.jpg",
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1540369975586&di=76f481d442a024156edfa27782a27bf5&imgtype=0&src=http%3A%2F%2Fa.hiphotos.baidu.com%2Fzhidao%2Fpic%2Fitem%2F1f178a82b9014a908ebdf9abab773912b31bee21.jpg"
          ],
          swiperItemIndex:1//定义最开始显示第几张图片
        }
      },
      methods:{
        onSwiperItemIndexChange (index) {
          console.log('demo item change', index)
        },
      }
    }
</script>

<style scoped>

</style>
