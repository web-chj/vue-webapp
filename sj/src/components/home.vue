<template>
  <div class="Home">
      <div class="Homeheader">手机商城</div>
      <div class="swipe">
        <mt-swipe :auto="4000">
          <mt-swipe-item><router-link to="goodDetail?id=4"><img src="../../static/img/banner1.jpg" alt="轮播图"></router-link></mt-swipe-item>
          <mt-swipe-item><router-link to="choose"><img src="../../static/img/banner2.jpg" alt="轮播图"></router-link></mt-swipe-item>
        </mt-swipe>
      </div>
      <div class="HomeList">
        <ul >
          <li><div @click="xuangou"><img src="../../static/img/1.png" alt="商品分类"></div></li>
          <li><div  @click="btn"><img src="../../static/img/2.png" alt="品牌日"></div></li>
          <li><div @click="toOrder"><img src="../../static/img/3.png" alt="我的订单"></div></li>
          <li><div @click="btn"><img src="../../static/img/4.png" alt="在线客服"></div></li>
        </ul>
      </div>
      <div class="main">
        <span >热门商品</span>
        <div class="main_box">
          <ul><!-- <img src="../assets/list1.jpg" alt="商品"> -->
            <li v-for="(todo,index) in todos" :id="todo.id"  @click="open(todo.id)" class="list">
                <div class="image">
                  <img v-bind:src="'.'+todo.img" alt="图片">
                </div>
                <div class="name">{{todo.name}}</div>
                <div class="nametwo">{{todo.nametwo}}</div>
                <div class="Price">￥{{todo.Price}}</div>
            </li>
          </ul>
        </div>
      </div>
  </div>
</template>

<script>
import { mapState,mapMutations,mapGetters  } from 'vuex';
import { Swipe, SwipeItem } from 'mint-ui';
import { MessageBox } from 'mint-ui';
export default {
  name:"home",
  data(){
    return{
      todos:[
        {
          "id":"1",
          "img":"/static/img/home/s2a.jpg",
          "name":"华为 畅享7 Plus",
          "nametwo":"优惠200元|限量促销",
          "Price":"2798"
        },
        {
          "id":"2",
          "img":"/static/img/home/s4a.jpg",
          "nametwo":"6.43英寸大屏|0.1s快速解锁",
          "name":"华为 nova 2S",
          "Price":"3498"
        },
        {
          "id":"3",
          "img":"/static/img/home/s6a.jpg",
          "name":"Galaxy C9Pro",
          "nametwo":"前置2400万像素",
          "Price":"2498"
        },
        {
          "id":"4",
          "img":"/static/img/home/s8a.jpg",
          "name":"三星 Galaxy S8",
          "nametwo":"后置双摄|免费镭射镌刻",
          "Price":"3998"
        }
        ,
        {
          "id":"5",
          "img":"/static/img/home/s11b.jpg",
          "name":"小米5X",
          "nametwo":"大屏美颜自拍",
          "Price":"1098"
        }
        ,
        {
          "id":"6",
          "img":"/static/img/home/s13b.jpg",
          "name":"小米6",
          "nametwo":"5.5英寸大屏|支持花呗分期",
          "Price":"1298"
        }
      ]
    }
  },

  methods:{
    open:function(id){
      this.$router.push({path:"goodDetail",query:{id:id}})
    },
    xuangou:function(){
      this.$router.push({path:"choose"})
    },
    toOrder:function(){
      this.$router.push({path:"order"})
    },
    btn:function(){
      MessageBox('提示', '未展示');
    }
  },
}
</script>
<style>
  .Home{
    border-bottom: 10px;
    background: white;
  }
   .Homeheader{
     width: 100%;
     z-index: 1;
     height: 1.3rem;
     line-height: 1.3rem;
     font-size: 0.65rem;
     text-align: center;
   }
   .swipe{
     height: 6.5rem;
     margin-top: 1px;
   }
   .swipe img{
      width: 100%;
      height: 6.5rem;
  }
  .main_box{
    /* margin-bottom: 34px;  */
    height: 339px;

  }
  .main span{
    display: block;
    height: 1.3rem;
    background: white;
    font-size: 0.35rem;
    line-height: 1.3rem;
    padding-left: 0.3rem;
    width: 50%;
  }
  .list {
    height: 7.3rem;
    background: white;
    float: left;
    box-sizing:border-box;
    width:50%;
    border-right: 1px solid #F4F4F4;
    border-top: 1px solid #cccccc;
  }
  .list span{
    display: block;
    color: red;
    padding-left: 0.5rem;
    padding-top: 0.1rem;
  }
  .main_box ul{
      overflow: hidden;
      margin-bottom: 1.5rem;
  }
  ul li{
    list-style: none;
  }
  .name{
    width: 80%;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    margin: auto;
    font-size: 0.37rem;
    padding-top: 0.8rem;
    font-weight: 800;
    text-align: center;
  }
    .nametwo{
      font-size: 0.01rem;
      text-align: center;
      padding-top: 0.15rem;
      font-family: "微软雅黑"
    }
    .Price{
      font-size: 0.33rem;
      color: red;
      margin: auto;
      /* padding: 0.1rem 0.9rem; */
      text-align: center;
      padding-top: 0.48rem;
      /* font-weight: bold; */
      font-size: 0.38rem;

    }
    .image{
      width: 100%;
      height: 4rem;
      background: white;
    }
    .image img{
      height: 3.3rem;
      width: 3.5rem;
      display: block;
      margin: auto;
      padding-top: 0.9rem;
    }
    .HomeList{
      width: 100%;
      height: 2.5rem;
      background: white;
      margin: 0 auto;
    }

    .HomeList>ul>li img{
      display: block;
      width: 48px;
      height: 68px;
      margin: 15px auto;
    }
    .HomeList>ul>li{
      width: 25%;
      float: left;
      margin: auto;
    }
</style>

