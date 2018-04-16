<template>
  <div class="information">
        <div class="informationHeader">
            <span>新闻信息</span>
        </div>
        <div class="informationMian" style="margin-top: 1.33rem;">
            <ul>
                <li v-for="(information,index) in informations" class="Mainlist" @click="open(information.id)" :id="information.id">
                    <h3 class="MainTitle" style="color:#434343"> {{information.title}}</h3  >

                    <div class="informationImg">
                        <img  v-bind:src="'.'+information.img" alt="图片">
                    </div>
                    <div class="infoFooter">
                        <span class="MianTime">{{information.time}}</span>
                        <mt-button class="mtButton" icon="more" type="primary" size="small">
                            阅读全文
                        </mt-button>
                    </div>
                </li>
            </ul>

        </div>
        <div class="informationfooter">

        </div>
  </div>
</template>

<script>
import {Button} from 'mint-ui'
export default {
    name:"information",
    data(){
        return{
          informations:[
            {
              "id":1,
              "title":"华为发布2017年年报：稳健经营，持续为客户创造价值",
              "time":"2018.03.30",
              "img":"/static/img/new1.png"
            },
            {
              "id":2,
              "title":"华为SmartPCC解决方案荣获“最佳5G演进服务化架构”奖",
              "time":"2018.04.12",
              "img":"/static/img/new2.png"
            },
            {
              "id":3,
              "title":"小米投资的黑鲨游戏手机发布：配独立手柄 售价2999元起",
              "time":"2018-04-13",
              "img":"/static/img/new3.png"
            },
            {
              "id":4,
              "title":"三星下月开始生产新一代iPhone的OLED面板",
              "time":"2018-04-14",
              "img":"/static/img/new4.png"
            }
          ]
        }
    },
    mounted:function(){
        //this.getDate()
    },
    methods:{
        getDate:function(){
            var _this=this;
            this.$http.get("/static/information.json").then(function(res) {
                for (var i = 0, len = res.body.informations.length; i < len; i++) {
                    var selData = res.body.informations[i];
                    var part = res.body.informations[i].name;
                    _this.informations.push(selData);
                }
            })
        },
        open:function(id){
            this.$router.push({path:"news",query:{id:id}})
        },
    }


}
</script>


<style>
  .information{
    position: absolute;
    width: 100%;
    z-index: 999;
    margin-bottom: 1.5rem;
  }
.informationHeader{
    position: fixed;
    width: 100%;
    -webkit-box-shadow: 0 0 10px #cecece;
    box-shadow: 0 0 10px #cecece;
    height: 1.3rem;
    line-height: 1.3rem;
    font-size: 0.35rem;
    padding-left: 0.3rem;
    background: white;
    top: 0;
    font-size: 0.41rem;
}
.informationHeader i{
    display: block;
    float: left;
    height: 50px;
    padding-left: 0.3rem;
    font-size: 22px;
    color: black;
}
.Mainlist{
    width: 100%;
    height: auto;
    background: white;
    margin-top: 5px;
    padding-top: 0.35rem;
}

.MainTitle{
    width: 77%;
    text-align: left;
    margin: 0 auto 0.4rem;
    color: rgb(67, 67, 67);
    font-size: 0.4rem
}
.infoFooter{
    position: relative;
    margin-top: 0.2rem;
}
.MianTime{
    width: 78%;
    margin: auto;
    display: block;
    line-height: 0.2rem;
    padding: 7px 36px;
    font-size: 0.3rem;
    position: absolute;
    top: 0;
    left: 0;
}
.mtButton{
    margin: 0;
    top:-5px;
    left: 65%;
}
.informationImg img{
    width: 100%;
    height: auto;
}
.Mainlist a{
    float: right;
    font-size: 0.3rem;
    margin-right: 0.75rem;
    margin-top: 0.2rem;
    color: black;
}
</style>
