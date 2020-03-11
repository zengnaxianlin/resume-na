<!--
 * @Author: zn 610039061@qq.com
 * @Date: 2020-02-11 18:05:14
 * @LastEditTime : 2020-02-11 22:41:48
 * @Description: 简历
 -->
<template>
  <div class="page-resume">
    <!-- 左侧个人信息 -->
    <div class="resume-aside">
      <div class="aside-content">
          <img src="./../assets/images/logo.png" class="aside-portrait">
          <div class="personal-desc">
              <p>曾娜</p>
              <p> Web前端开发工程师 </p>
              <p> 女 / 1992.05 </p>
              <span class="work-year">3年工作经验</span>
          </div>
          <div class="aside-preview">
              <p>
                  <i></i>
                  <a href="mailto:610039061@qq.com">610039061@qq.com</a>
              </p>
              <p>
                  <i></i>
                  <a href="tel:13711504803">13711504803</a>
              </p>
              <p>
                  <i></i>
                  <a onclick="window.open('https://zengnaxianlin.github.io')">https://zengnaxianlin.github.io</a>
              </p>
              <p>
                  <span>在线简历</span>
                  <a onclick="window.open('https://zengnaxianlin.github.io/resume')">https://zengnaxianlin.github.io/resume</a>
              </p>
          </div>
          <div class="black-item mt16">
              <div class="header-title">
                  <p>教育经验</p>
              </div>
              <p>宜春学院<br/>数学与计算机学院</p>
              <p>2012.9 - 2016.6</p>
              <p>计算机科学与技术 - 本科</p>
          </div>
          <div class="black-item" v-if="personalEvaluation">
              <div class="header-title">
                  <p>个人评价</p>
              </div>
              <ul class="person-introduction">
                  <li v-for="(item,index) in personalEvaluation" :key="index" v-html="item"></li>
              </ul>
          </div>
          <div class="black-item" v-if="workExperience">
              <div class="header-title">
                  <p>工作经验</p>
              </div>
              <div class="work-exp" v-for="(item,index) in workExperience" :key="index">
                <p class="work-exp-company">{{item.companyName}}</p>
                <p class="work-time">{{item.time}}</p>
                <p class="work-exp-main">主要职责：{{item.mainWork}}</p>
              </div>
          </div>
      </div>
    </div>
    <!-- 右侧个人内容 -->
    <div class="resume-content">
      <div>
        <div class="black-item" v-if="projects">
            <div class="header-title">
                <p>项目经验</p>
            </div>
            <div v-for="(item,index) in projects" :key="index" class="project">
              <p class="pro-name">
                {{ item.projectName }}
                <span class="pro-time">{{ item.time }}</span>
              </p>
              <p><span class="pro-title">主要技术：</span><span v-html="item.mainSkills"></span></p>
              <p class="pro-production"><span class="pro-title">项目描述：</span>{{ item.production }}</p>
              <p class="pro-modules"><span class="pro-title">负责模块：</span>{{ item.modules }}</p>
              <p><span class="pro-title">项目地址：</span><a :href="item.addr" target="_blank">{{ item.addr }}</a></p>
            </div>
        </div>
      </div>
    </div>
    <!-- 下载简历 -->
    <div class="pdf-btn">
        <span>下载PDF简历</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'resume',
  data () {
     return {
      personalEvaluation: [
          '善于根据需求提供合适的技术解决方案、使用各种工具提高生产力, 拥有清晰的产品思维和较强的沟通能力, 能与团队合作融洽。',
          '良好的 <em>JavaScript</em> / <em>ES6+</em> 基础; 乐于钻研学习新技术, 时刻关注行业动态拓展视野',
          '熟悉使用 <em>Vue</em> 框架进行开发；熟悉使用 <em>wepy</em> 框架进行小程序开发',
          '熟悉使用 <em>Node Express</em> 开发，会使用基于 <em>node</em> 的各种前端构建工具 <em>gulp</em>、<em>grunt</em> 等',
          '持续的优化前端性能体验和页面响应速度，保证兼容性和执行效率',
          '具备良好的编程风格，代码简洁整齐，能熟练编写符合 <em>W3C</em> 标准的高效率代码',
      ],
      workExperience:[
        {
          'companyName':'广州企成信息技术有限公司',
          'time':'2015-03 至 2016-03',
          'mainWork':'负责公司官网和微信公众号的前端项目开发'
        },
        {
          'companyName':'广州市零空信息技术有限公司',
          'time':'2016-03 至 2018-10',
          'mainWork':'负责公司产品的前端项目开发'
        }
      ],
      projects:[
        {
          'projectName':'魔法隧道',
          'time':'2016-03 至 2016-08',
          'mainSkills':'<em>jquery</em> 、<em>bootstrap</em>',
          'production':'魔法隧道提供免费的智能网络穿透，通过自主研发的穿透技术，可供多线路支持运行，让用户无需公网IP、无需路由端口映射、不用机房托管便可轻轻松松实现家中建站、远程桌面、游戏服务器、ERP互联等功能',
          'modules':'登录注册模块、个人中心、隧道控制中心',
          'addr':'http://www.mofasuidao.cn'
        },
        {
          'projectName':'毅起付-商家智慧助手',
          'time':'2017-12 至 2018-06',
          'mainSkills':'<em>vue</em> 、<em>router</em> 、<em>vuex</em> 、<em>ElementUI</em> 、<em>axios</em> 、<em>webpack</em>',
          'production':'毅起付商家智慧助手是一款为线下商户提供智慧支付及营销解决方案的聚合支付产品。',
          'modules':'登录注册模块、会员管理、签约管理、服务商管理、商户管理、门店管理、权限管理系统、佣金管理、广告联盟等',
          'addr':'https://sjzs.hydosky.com'
        },
        {
          'projectName':'联通工业互联网装备云项目',
          'time':'2019-08 至 2020-01',
          'mainSkills':'<em>vue</em> 、<em>router</em> 、<em>vuex</em> 、<em>ElementUI</em> 、<em>axios</em> 、<em>sass</em> 、<em>webpack</em> 、<em>ES6/ES7</em>',
          'production':'毅起付商家智慧助手是一款为线下商户提供智慧支付及营销解决方案的聚合支付产品。',
          'modules':'登录注册模块、会员管理、签约管理、服务商管理、商户管理、门店管理、权限管理系统、佣金管理、广告联盟等',
          'addr':'https://sjzs.hydosky.com'
        },
        {
          'projectName':'联通云护理疫情版微信小程序',
          'time':'2020-01 至 2020-03',
          'mainSkills':'<em>wepy</em> 、<em>wantUI</em> 、<em>less</em> 、<em>ES6/ES7</em> ',
          'production':'毅起付商家智慧助手是一款为线下商户提供智慧支付及营销解决方案的聚合支付产品。',
          'modules':'首页模块、患者填报信息模块、健康医码模块，医院主页模块，预检分诊模块，导出统计模块，扫一扫模块等',
          'addr':'https://sjzs.hydosky.com'
        },
        {
          'projectName':'联通云护理疫情版App',
          'time':'2020-02 至 2020-03',
          'mainSkills':'<em>uniapp</em> 、<em>sass </em> 、<em>ES6/ES7</em> ',
          'production':'毅起付商家智慧助手是一款为线下商户提供智慧支付及营销解决方案的聚合支付产品。',
          'modules':'登录模块，首页模块、健康宣教，更多模块，健康医码模块，预检分诊模块，导出统计模块，扫一扫模块，我的模块等',
          'addr':'https://sjzs.hydosky.com'
        }
      ]
    };
  }
}
</script>

<style lang="scss" scoped>
    //$theme: #ffb6b0;
    $theme: #fb8e85;
    $textColor:#666;

    @mixin themeBg ($opacity){
        //background-color: rgba(255,182,176, $opacity);
        background-color: rgba(251,142,133, $opacity);
    }

    .page-resume{
        width: 1024px;
        min-height: 500px;
        background-color: #fff;
        margin: 50px auto;
        box-shadow: 0 0 15px silver;
        color: $textColor;
        display: flex;

        .resume-aside{
            -webkit-box-flex: 3;
            -ms-flex: 3;
            flex: 3;
            display: -webkit-box;
            display: -ms-flexbox;
            display: flex;
            -webkit-box-direction: normal;
            -ms-flex-direction: column;
            flex-direction: column;
            padding: 40px;
            background-color: #FFFAF6;
            align-items: center;
            text-align: center;

            .aside-content{

                .aside-portrait{
                    width: 240px;
                    height: 240px;
                    border-radius: 50%;
                }

                .personal-desc{

                    .work-year{
                        color: #fff;
                        @include themeBg(1);
                        padding:6px 10px;
                        border-radius:20px;
                        font-size:14px;
                    }
                }

                .aside-preview{
                    p{
                        margin-bottom: 6px;
                    }

                    a{
                        color: $textColor;
                        cursor: pointer;
                        margin-left: 10px;
                        text-decoration:underline;

                        &:hover{
                            opacity: .7;
                        }
                    }
                }

                .person-introduction{
                  padding:0;
                  font-size:14px;
                  li{
                    text-align:left;
                    padding-bottom:10px;
                  }
                }

                .header-title{
                  color: #D246B2;
                  font-size: 22px;
                  font-weight: 700;
                }

                .work-exp{
                  margin-bottom:25px;
                  text-align:left;
                  .work-exp-company{
                    font-size: 16px;
                    font-weight: 700;
                    margin-bottom:6px;
                  }
                  .work-time{
                    font-size:12px;
                    font-weight:700;
                    margin:0;
                  }
                  .work-exp-main{
                    margin:0;
                  }
                }
            }
        }

        .resume-content{
            display: flex;
            flex: 6;
            padding: 20px 30px;
            .black-item{
              .header-title{
                position:relative;
                p{
                  font-size: 22px;
                  font-weight: 700;
                  text-align:center;
                  width: 200px;
                  line-height: 1.8;
                  margin: 0 auto;
                  color: white;
                  border-radius: 30px;
                  @include themeBg(1);
                }
                &:before,&:after{
                  position: absolute;
                  display: block;
                  top: 19px;
                  content: "";
                  background: $theme;
                  height: 2px;
                  width: calc(50% - 120px);
                }
                &:before{
                  left:0;
                }
                &:after{
                  right:0;
                }
              }
            }
            .project{
              font-size:14px;
              margin-top:50px;
              .pro-name{
                font-size:20px;
                font-weight:600;
                margin:0;
                .pro-time{
                  font-size:14px;
                  color:$textColor;
                  font-weight:bold;
                }
              }
              .pro-title{
                font-weight: 700;
              }
            }
            a{
                color: #333;
                cursor: pointer;
                text-decoration:underline;

                &:hover{
                    opacity: .7;
                }
            }

        }

        .black-item{
            color: #555;
            .header-title{
                p{
                    color: $theme;
                    position:relative;
                    &:before,&:after{
                      position: absolute;
                      display: block;
                      top: 16px;
                      content: "";
                      background: $theme;
                      height: 2px;
                      width: calc(50% - 60px);
                    }
                    &:before{
                      left:0;
                    }
                    &:after{
                      right:0;
                    }
                }
            }
        }

        .pdf-btn{
            line-height: 3;
            font-size: 14px;
            color: #fff;
            border-radius: 50px;
            background-color: $theme;
            position: fixed;
            right: 40px;
            bottom: 40px;
            box-shadow: 0 0 15px silver;
            cursor: pointer;

            span{
                display: block;
                padding: 0 20px;
            }

            &:hover{
                color: $theme;
                background-color: #fff;
            }
        }
    }
    .mt16{
      margin-top:16px;
    }

    @media screen and (max-width: 1049px){
      .page-resume{
        margin:0;
        width: 100%;
        display:block;

      }
      .resume-aside{
        padding-top:80px;
      }
    }


</style>
