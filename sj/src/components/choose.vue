<template>
  <div class="choose">
        <div class="_choose_header">
            <a href="#" @click="choose">
                <i class="iconfont icon-552cc14536532"></i>
            </a>
            <span>商品分类</span>
        </div>
        <div class="_choose_twoMain">
            <mt-navbar v-model="selected" >
                <mt-tab-item id="tab-container1">全部</mt-tab-item>
                <mt-tab-item id="tab-container2">华为系列</mt-tab-item>
                <mt-tab-item id="tab-container3">三星系列</mt-tab-item>
                <mt-tab-item id="tab-container4">小米系列</mt-tab-item>
            </mt-navbar>

            <mt-tab-container v-model="selected" swipeable>
                <mt-tab-container-item id="tab-container1">
                    <ul style="margin-top: 2px;">
                        <li class="_chooseList" v-for="(choose,index) in chooses" :id="choose.id" @click="open(choose.id)">
                            <img v-bind:src="'.'+choose.ImageOne" alt="图片">
                            <p>{{choose.name}}</p>
                            <p style="font-size: 0.3rem;">{{choose.nametwo}}</p>
                            <div>￥{{choose.Price}}</div>
                        </li>
                    </ul>
                </mt-tab-container-item>
                <mt-tab-container-item id="tab-container2">
                    <ul style="margin-top: 2px;">
                        <li class="_chooseList" v-for="(choose,index) in motos" :id="choose.id" @click="open(choose.id)">
                            <img v-bind:src="'.'+choose.ImageOne" alt="图片">
                            <p>{{choose.name}}</p>
                            <p style="font-size: 0.3rem;">{{choose.nametwo}}</p>
                            <div>￥{{choose.Price}}</div>
                        </li>
                    </ul>
                </mt-tab-container-item>
                <mt-tab-container-item id="tab-container3">
                     <ul style="margin-top: 2px;">
                        <li class="_chooseList" v-for="(choose,index) in MotoZs" :id="choose.id" @click="open(choose.id)">
                            <img v-bind:src="'.'+choose.ImageOne" alt="图片">
                            <p>{{choose.name}}</p>
                            <p style="font-size: 0.3rem;">{{choose.nametwo}}</p>
                            <div>￥{{choose.Price}}</div>
                        </li>
                    </ul>
                </mt-tab-container-item>
                <mt-tab-container-item id="tab-container4">
                    <ul style="margin-top: 2px;">
                        <li class="_chooseList" v-for="(choose,index) in z2s" :id="choose.id" @click="open(choose.id)">
                            <img v-bind:src="'.'+choose.ImageOne" alt="图片">
                            <p>{{choose.name}}</p>
                            <p style="font-size: 0.3rem;">{{choose.nametwo}}</p>
                            <div>￥{{choose.Price}}</div>
                        </li>
                    </ul>
                </mt-tab-container-item>
            </mt-tab-container>

        </div>
  </div>
</template>


<script>
import { Navbar, TabItem } from 'mint-ui';
export default {
  name:"choose",
  data(){
      return{
          selected:"tab-container1",
          chooses:[
          {
            "id":"1",
            "ImageOne":"/static/img/home/s2a.jpg",
            "name":"华为 畅享7 Plus",
            "nametwo":"优惠200元|限量促销",
            "Price":"2798   "
          },
          {
            "id":"2",
            "ImageOne":"/static/img/home/s4a.jpg",
            "nametwo":"6.43英寸大屏|0.1s快速解锁",
            "name":"华为 nova 2S",
            "Price":"3498"
          },
          {
            "id":"3",
            "ImageOne":"/static/img/home/s6a.jpg",
            "name":"Galaxy C9Pro",
            "nametwo":"前置2400万像素",
            "Price":"2498"
          },
          {
            "id":"4",
            "ImageOne":"/static/img/home/s8a.jpg",
            "name":"三星 Galaxy S8",
            "nametwo":"后置双摄|免费镭射镌刻",
            "Price":"3998"
          }
          ,
          {
            "id":"5",
            "ImageOne":"/static/img/home/s11b.jpg",
            "name":"小米5X",
            "nametwo":"大屏美颜自拍",
            "Price":"1098"
          }
          ,
          {
            "id":"6",
            "ImageOne":"/static/img/home/s13b.jpg",
            "name":"小米6",
            "nametwo":"5.5英寸大屏|支持花呗分期",
            "Price":"1298"
          }

        ],
          motos:[
          {
            "id":"1",
            "ImageOne":"/static/img/home/s2a.jpg",
            "name":"华为 畅享7 Plus",
            "nametwo":"优惠200元|限量促销",
            "Price":"2798   "
          },
          {
            "id":"2",
            "ImageOne":"/static/img/home/s4a.jpg",
            "nametwo":"6.43英寸大屏|0.1s快速解锁",
            "name":"华为 nova 2S",
            "Price":"3498"
          }
        ],
          MotoZs:[
          {
            "id":"3",
            "ImageOne":"/static/img/home/s6a.jpg",
            "name":"Galaxy C9Pro",
            "nametwo":"前置2400万像素",
            "Price":"2498"
          },
          {
            "id":"4",
            "ImageOne":"/static/img/home/s8a.jpg",
            "name":"三星 Galaxy S8",
            "nametwo":"后置双摄|免费镭射镌刻",
            "Price":"3998"
          }
        ],
          z2s:[
          {
            "id":"5",
            "ImageOne":"/static/img/home/s11b.jpg",
            "name":"小米5X",
            "nametwo":"大屏美颜自拍",
            "Price":"1098"
          },
          {
            "id":"6",
            "ImageOne":"/static/img/home/s13b.jpg",
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
        choose:function(){
            this.$router.go(-1)
        },
  }
}
</script>

<style>
.choose{
    position: absolute;
    background: white;
    width: 100%;
    z-index:999;
    margin-bottom: 1.5rem;
}
._choose_header{
    width: 100%;
    z-index: 1;
    height: 1.3rem;
    line-height: 1.3rem;
    font-size: 12px;
    background: white;
    position: fixed;
    -webkit-box-shadow: 0 0 10px #cecece;
    box-shadow: 0 0 10px #cecece;
    text-align: center;
    font-size: 0.41rem;
}
._choose_header i{
    display: block;
    float: left;
    height: 50px;
    padding-left: 0.3rem;
    font-size: 0.71rem;
    color: black;
}
._choose_twoMain{
    margin-top: 1.32rem;
}
._chooseList{
    height: 6.3rem;
    background: white;
    float: left;
    box-sizing: border-box;
    width: 50%;
    border-right: 1px solid #F4F4F4;
    border-bottom: 1px solid #F4F4F4;
    float: left;
    margin-top: 1px;
    list-style: none;
}
._chooseList p{
    width: 94%;
    overflow: hidden;
    text-overflow: ellipsis;
    margin: auto;
    font-size: 0.35rem;
    text-align: center;
}
._chooseList div{
    text-align: center;
    color: red;
    margin-top: 10px;
}
._chooseList img{
    height: 3.2rem;
    width: 4rem;
    display: block;
    margin: auto;
    padding: 0.5rem;
}
</style>
