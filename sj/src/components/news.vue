<template>
  <div class="news">
      <div class="newsHeader">
            <a href="#" @click="news">
                <i class="iconfont icon-552cc14536532"></i>
            </a>
            <span>新闻详情</span>
        </div>
        <div class="newsMain" v-for="(news,index) in list">
            <h3 class="newsTitle">{{news.title}}</h3>
            <span class="newsTime">{{news.time}}</span>
            <div style="margin-top: 0.6rem;">
                <div class="newsBox" v-for="box in news.boxs">
                    <p >{{box.p}}</p>
                </div>
            </div>

        </div>
        <div class="newsFooter"></div>
  </div>
</template>
<script>
export default {
  name:"news",
  data(){
      return{
        lists:[
    {
      "id":1,
      "title":" 华为发布2017年年报：稳健经营，持续为客户创造价值",
      "time":"2018.03.30",
      "boxs":[
      {
        "p":"   [中国，北京，2018年4月12日] 今日，华为在中国信息通信研究院，率先以100%通过率，完成由IMT-2020(5G)推进组组织的中国5G技术研发试验第三阶段基于非独立组网（NSA）的核心网关键技术与业务流程测试。本次5G 非独立组网（NSA）测试是中国5G技术研发试验测试的重要组成部分，对运营商早期快速实现5G商用部署具有重要意义。"
      },
      {
        "p":"　　本次测试基于华为在2018年世界移动大会上发布的商用5G核心网解决方案，完成了包括核心网CUPS(控制面与用户面分离)架构下的网关选择、支持5G超高带宽、支持5G NR独立计费、支持终端LTE与NR（5G 新空口）双连接、终端接入能力管理等关键功能的验证，同时验证了基于5G 非独立组网（NSA）标准的终端注册、业务请求、移动性管理、会话管理等关键业务流程。"
      },
      {
        "p":"　　5G技术研发试验由IMT-2020(5G)推进组组织实施，其中5G网络部分的测试在5G试验工作组中，由中国信息通信研究院与中国移动、中国电信、中国联通三家运营商组成的测试组共同完成。验证测试共分为三个阶段，在此前第一和第二阶段华为5G核心网均率先以优异成绩顺利完成，包括核心网服务化架构、网络切片关键技术、移动边缘计算等技术方案以及样机设备的验证。"
      }
    ]
    }
  ,
    {
      "id":2,
      "title":"华为SmartPCC解决方案荣获“最佳5G演进服务化架构”奖",
      "time":"2018.04.12",
      "boxs":[
      {
        "p":"　　[西班牙，马德里，2018年4月12日] 在2018年策略管理峰会上，华为SmartPCC（策略与计费控制）解决方案凭借微服务级的生命周期管理、灵活的策略编排和敏捷业务创新等能力，荣获“最佳5G演进服务化架构（Best Service-based Architecture for 5G Evolution）”奖。"
      },
      {
        "p":"　　SmartPCC作为业务感知的智能管道，为电信运营商的全业务场景实施策略控制管理。其采用面向5G的服务化架构，实现敏捷部署、秒级弹性，加速业务创新；采用DevOps一体化运营模式，实现业务按需部署、自动化测试和快速上线；能迅速匹配千行百业的差异化需求，为用户提供极致业务体验。华为SmartPCC解决方案提供传统平台与云化平台的混合组网方式，保护运营商传统资产，保障网络功能向5G平滑演进。"
      },
      {
        "p":"　　华为云核心网融合数据领域总经理许曦表示：“感谢业界对华为SmartPCC策略管理能力和服务化实践的认可。随着5G时代的到来，策略管理将在泛接入、多业务、多行业的端到端QoS保障上发挥更加关键的作用。我们将在商业模型、技术架构、演进策略等方面做到更好，帮助运营商构建灵活、敏捷、开放的统一策略控制中心，开启5G时代的新商业、新运营、新体验，驱动产业发展与商业成功。”"
      },
      {
        "p":"　　截至2018年第一季度，华为SmartPCC解决方案已应用于110多个国家的260多个运营商，并已与中国移动、韩国LG U+等全球领先运营商开展了5G技术的验证与合作"
      }
    ]
    }
  ,
    {
      "id":3,
      "title":"小米投资的黑鲨游戏手机发布：配独立手柄 售价2999元起",
      "time":"2018-04-13",
      "boxs":[
      {
        "p":"　　腾讯数码讯 北京时间4月13日，小米投资的电竞手机——黑鲨手机正式发布，这也是从去年Razer推出游戏手机这个概念之后，国内首个推出的游戏手机。黑鲨手机除了本身配置出色之外，还未手机单独定制了手柄配件。这款手机定价2999元起。"
      },
      {
        "p":"　　虽说是主打游戏的产品，但是归根结底黑鲨首先还是一款手机产品。黑鲨手机没有之前网络上传闻的PSP造型，而它使用了一个左右全对称的传统造型设计，以黑色为主题色，辅以绿色作为配色点缀。"
      },
      {
        "p":"　　手机整体的造型在背面有一定的创新，首先是背面拥有一个X形的纹路设计，按照官方的说法，这样可以提供出色的横向握持感受，便于用户游戏时使用。同时背面有一个黑鲨LOGO造型的绿色呼吸灯，可以实现根据声音有节奏的闪动。"
      }
    ]
    },
    {
      "id":4,
      "title":"三星下月开始生产新一代iPhone的OLED面板",
      "time":"2018-04-14",
      "boxs":[
      {
        "p":"　　腾讯数码讯（肖恩）苹果在去年9月正式发布了全新的iPhone X，但由于生产环节存在的问题，这款手机直到11月份才终于发售。为了避免相同问题再次发生，苹果今年可能会提早开始新一代iPhone的生产。"
      },
      {
        "p":"　　根据韩国ETNews报道，三星目前已经开始为2018款iPhone准备OLED面板的生产了，5月份的初期产量在200-300万之间，6月份预计恢复翻倍。"
      },
      {
        "p":"　　而根据之前的报道，苹果将在今年推出3款iPhone，其中两款使用了OLED面板，分别是6.5英寸的iPhone X和第二代iPhone X。更有意思的是，苹果和三星目前仍然在商谈OLED面板的价格。"
      },
      {
        "p":"　　“谈判仍然在进行当中，”ETNews的报道指出，“三星高管最近到访苹果总部的举动也没能实现相互理解。为了满足苹果更低的价格要求，三星提出供应S9+所使用的Y-Octa面板。这种面板的生产成本更低，但良品率可能无法满足苹果的数量要求。”"
      },
      {
        "p":"　　“谈判仍然在进行当中，”ETNews的报道指出，“三星高管最近到访苹果总部的举动也没能实现相互理解。为了满足苹果更低的价格要求，三星提出供应S9+所使用的Y-Octa面板。这种面板的生产成本更低，但良品率可能无法满足苹果的数量要求。”"
      }
    ]
    }

  ],
        list:[]
      }
    },
    mounted:function(){
        this.getData()
    },
    methods:{
        getData:function(){
            var id=this.$route.query.id;
            //var _this = this;
            //this.$http.get("/static/information.json").then(function(res) {
                //for (var i = 0; i < res.body.list.length; i++) {
                    //if (res.body.list[i].id == id) {
                        this.list.push(this.lists[id-1])
                    //}
                //}
            //})
        },
        news:function(){
            this.$router.go(-1)
        }
    },
}
</script>



<style>
.news{
    position: absolute;
    width: 100%;
    z-index: 999;
    margin-bottom: 1.5rem;
}
.newsHeader{
    position: fixed;
    width: 100%;
    -webkit-box-shadow: 0 0 10px #cecece;
    box-shadow: 0 0 10px #cecece;
    height: 1.3rem;
    line-height: 1.3rem;
    font-size: 0.41rem;
    padding-left: 0.3rem;
    background: white;
    top: 0;
    text-align: center;
}
.newsHeader i{
    display: block;
    float: left;
    height: 50px;
    font-size: 0.71rem;
    color: black;
}
.newsMain{
    margin-top: 0.1rem;
    background: white;
}
.newsTitle{
    width: 282px;
    margin: auto;
    text-align: center;
}
.newsTime{
    text-align: center;
    display: block;
    margin-top: 0.3rem;
}
.newsBox p{
    width: 296px;
    margin: auto;
    font-size: 0.44rem;
    line-height: 150%;
    font-family: 微软雅黑, sans-serif;
    margin-top: 0.3rem;
}
.newsBox img{
    width: 9.3rem;
    display: block;
    margin: auto;
}

</style>
