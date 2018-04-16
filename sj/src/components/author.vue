<template>
  <div class="Author">
      <div class="AuthorHeader">
        <router-link to="my">
          <i class="iconfont icon-552cc14536532"></i>
        </router-link>
          关于我与项目
      </div>
      <div class="AuthorMain">
        <h2>我</h2>
        <div>
          <mt-button class="pLeft">Q Q：</mt-button>2321979082
        </div>
        <div>
          <mt-button class="pLeft">邮箱：</mt-button>2321979082@qq.com
        </div>
         <h2>项目介绍</h2>
        <div>
          <mt-button class="pLeft">技术：</mt-button>
          <span v-for="(tmp,i) in list">
            <mt-button @click.native="handleClick(i)">{{tmp.name}}</mt-button>
          </span>
          <mt-popup class="mtPopup" pop-transition="popup-fade" modal="true" v-model="popupVisible">
              {{list[i].text}}
          </mt-popup>
        </div>
        <div>
          <mt-button class="pLeft">功能：</mt-button>
          <div class="gongNeng">
            <p>首页轮播图效果、链接跳转</p>
            <p>商品详情列表、轮播效果</p>
            <p>商品立即购买、加入购物车</p>
            <p>购物车加减数量、删除商品及结算清空</p>
            <p>商品删除结算、商品订单删除</p>
            <p>模拟支付成功后加入订单</p>
            <p>Localstorage本地存储数据</p>
          </div>
        </div>
            <mt-button @click="toHome" class="myButton"  type="primary" size="small">
                前往首页
            </mt-button>
      </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';
import {Button,Popup} from 'mint-ui';

export default {
    data () {
      return {
        popupVisible:false,
        i:0,
        list:[
          {
            name:"vue2.0",
            text:"构建用户界面的 MVVM 框架，核心思想是：数据驱动、组件系统"
          },
          {
            name:"vue-cli",
            text:"vue的脚手架工具"
          },
          {
            name:"webpack",
            text:"前端资源加载/打包工具"
          },
          {
            name:"vue-router+vue-resource",
            text:"官方提供的路由器+服务器通讯(请求数据)"
          },
          {
            name:"vuex",
            text:"专为 vue.js 应用程序开发的状态管理模式，就是管理数据的"
          },
          {
            name:"mint-ui",
            text:"饿了么前端团队推出的 Mint UI 是一个基于 vue.js 的移动端组件库"
          }
        ]
      }
    },
    methods: {
      handleClick: function(i) {
        this.i=i;
        this.popupVisible = true
      },
      toHome:function(){
        this.$router.push("/home")
      }
    }
}
</script>

<style>
.AuthorMain h2{
  margin: 0.5rem 0;
}
.myButton{
  margin: 0.6rem 0;
}
.AuthorMain>div{
  text-align: left;
}
.gongNeng p{
  text-align: center;
}
.mtPopup{
  text-align: center;
   border-radius:5px;
   padding: 20px;
   background-color: #ECF6FB;
   color: #26A2FE;
   font-size: 0.55rem;
   width: 150px;

}
.Author{
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 999;
  background-color: #ECF6FB;
  margin-bottom: 1.5rem;
}
.AuthorHeader{
    position: fixed;
    top: 0;
    width: 100%;
    height: 1.3rem;
    line-height: 1.3rem;
    background: white;
    padding-left: 0.3rem;
    -webkit-box-shadow: 0 0 10px #cecece;
    box-shadow: 0 0 10px #cecece;
    z-index: 1;
    font-size: 0.41rem;
}
.AuthorMain{
    margin-top: 1.6rem;
    font-size: 0.4rem;
    text-align: center;
}

.AuthorHeader i{
    display: block;
    float: left;
    height: 50px;
    font-size: 0.71rem;
    color: black;
    width: 0.9rem;
}

</style>
