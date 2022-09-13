<template>
  <div class="moreactive">
    <!-- 面包屑导航 -->
    <div class="crumb">
      <div>混合制项目</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div>管理者进阶-腾飞班</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div style="font-weight: 700; font-size: 16px">活动详情</div>

      <div class="preNext">
        <button class="btn btn01"></button>
        <span class="content">上一个</span>
        <span class="content" style="margin-left: 31px">下一个</span>
        <button class="btn btn02"></button>
      </div>
    </div>
    <!-- 面包屑导航 -->

    <!-- 基本信息 -->
    <div class="bascinfo">
      <div style="margin-left: 46px">
        <div class="title">【其他活动】管理者进阶腾飞班 - 专属线下活动</div>
        <div class="time" style="margin-top: 26px">
          <img width="15px" height="17px" src="../../assets/image/time.png" />
          <div style="margin-left: 8px">2022-07-20 20:00-21:00</div>
        </div>
        <div class="time" style="margin-top: 23px">
          <img
            width="16px"
            height="18px"
            src="../../assets/image/position.png"
          />
          <div style="margin-left: 8px">大族广场</div>
        </div>
      </div>
      <div class="btn">签到</div>
    </div>
    <!-- 基本信息 -->

    <!-- 详细信息 -->
    <div class="detailinfo">
      <div class="detail">
        <div class="detailT">
          <div class="" style="margin-left: 48px; margin-right: 48px">
            <div class="title">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/book.png"
              />
              <div class="text">课程详情</div>
              <div class="box"></div>
            </div>
            <div style="display: flex; align-items: center">
              <div class="content">
                写字楼介绍 <br />
                大族广场写字楼采用国际顶级硬件设施，美国OTIS电梯、麦克维尔中央空调、高端安防系统等商务空间新标准匹配项目在亦庄地标综合体的形象。写字楼空间设计由亚洲著名的
                室内空间设计大师之一梁景华设计，写字楼群由六栋(T1—T6)呈舰队排列的5A写字楼构成形成独特的舰队造型。
                <br />
                购物中心介绍 <br />
                大族广场Mall&More位于北京经济技术开发区核心商圈荣华路，由荷兰鹿特丹缤纷市场设计师HANS
                VAN DALEN
                主持设计,秉持自然与未来和谐共生理念,倡导乐活、有机、绿色环保的生活方式,传递生活美学。
                <br />
                大族广场Mall&More汇集众多知名优质品牌,7FRESH生鲜超市、CGV星聚汇影城、中信书店、源力悦体等,集购物、餐饮、娱乐、文化于一体,丰富的业态品类为消费者提供城市
                生活的第三空间感受。<br />
                大族广场Mall&More以人为本,不断提升服务水平,升级消费购物体验,致力于营造更加舒适的购物环境与空间,打造有温度的品牌。同时根据春夏秋冬四季策划丰富多样的大型主题
                活动；为会员设置专属的沙龙活动，打造专属会员日等,与顾客近距离产生情感上的互动与链接,为城市人们提供自由、放松、愉悦的社交空间与精神的栖息地。<br />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="teacher">
        <div class="title">
          <img
            style="width: 24px; height: 20px"
            src="../../assets/image/call.png"
          />
          <div class="text">活动公告</div>
          <div class="box"></div>
        </div>
        <div class="content">
          为拓宽人民群众的表达途径、畅听民意，及时了解
          和解决人民群众反映强烈的公共法律服务问题，我
          局将在浈江区公共法律服务中心开展领导干部接待
          活动，现将2022年8月的活动安排公告如下：<br />
          一、接待时间 <br />
          工作日上午9:00-12:00。<br />
          二、接待地点<br />
          浈江区公共法律服务中心（浈江区新韶镇乐土路3号
          曲仁田螺冲党群服务中心一楼）。<br />
          三、接待受理范围 <br />（一）听取人民群众对公共法律服务工作的批评和
          意见建议。 <br />（二）解答或接收公共法律服务相关业务咨询。<br />
        </div>
      </div>
    </div>
    <!-- 详细信息 -->
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "MoreActive",
  setup() {
    const state = reactive({
      activeName: "first",
    });
    const handleClick = (tab, event) => {
      console.log(tab, event);
    };
    return {
      ...toRefs(state),
      handleClick,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.moreactive {
  .crumb {
    color: #fff;
    display: flex;
    font-size: 14px;
    line-height: 24px;
    position: relative;
  }

  .preNext {
    position: absolute;
    right: 0px;
    .content {
      font-size: 14px;
      color: #fff;
      width: 43px;
      height: 14px;
      display: inline-block;
      position: relative;
      top: -6px;
    }
    .btn {
      width: 23px;
      height: 23px;
      border-radius: 50%;
      border: 0;
    }
    .btn01 {
      background-image: url("../../assets/image/prev.png");
    }
    .btn02 {
      background-image: url("../../assets/image/next.png");
    }
  }
  .bascinfo {
    width: 100%;
    height: 180px;
    border-radius: 8px;
    background-color: rgba(255, 255, 255, 1);
    margin-top: 37px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .btn {
      width: 146px;
      height: 46px;
      background: #2478ff;
      border-radius: 4px;
      box-shadow: 0px 1px 8px 0px rgba(56, 125, 247, 0.7);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 14px;
      font-weight: 800;
      line-height: 24px;
      cursor: pointer;
      margin-right: 96px;
    }
    .title {
      font-size: 20px;
      font-weight: 800;
      color: #333333;
      line-height: 24px;
      margin-left: -9px;
    }
    .time {
      font-size: 14px;
      color: #6e7b84;
      line-height: 24px;
      display: flex;
      align-items: center;
    }
  }
  .detailinfo {
    width: 100%;
    margin-top: 20px;
    display: flex;
    .detail {
      flex: 1;
      margin-right: 20px;
      .detailT {
        height: 670px;
        background: #ffffff;
        border-radius: 8px;
        color: rgba(51, 51, 51, 1);
        .title {
          display: flex;
          align-items: center;
          padding-top: 39px;
          position: relative;
        }
        .title .text {
          margin-left: 8px;
          font-size: 16px;
          color: rgba(51, 51, 51, 1);
          font-weight: 800;
        }
        .title .box {
          width: 75px;
          height: 10px;
          background-color: rgba(36, 120, 255, 0.15);
          position: absolute;
          left: 23px;
          top: 53px;
        }
        .content {
          margin-left: 8px;
          font-size: 14px;
          color: rgba(51, 51, 48, 1);
          font-weight: 500;
          line-height: 35px;
          margin-top: 30px;
        }
      }
      .detailB {
        min-height: 363px;
        background: #ffffff;
        border-radius: 8px;
        margin-top: 20px;
        .el-tabs__item {
          height: 69px;
          padding: 25px 7px 0px 52px;
          font-size: 14px;
          font-weight: 500;
        }
        .el-tabs__nav-wrap::after {
          background-color: rgba(56, 125, 247, 0.2);
        }
        .enclosure {
          height: 89px;
          margin-left: 51px;
          margin-right: 40px;
          // border-bottom: 1px solid rgba(56, 125, 247, 0.2);
          display: flex;
          justify-content: space-between;
          align-items: center;
          .enclosureL {
            display: flex;
            align-items: center;
            font-size: 14px;
            font-weight: 400;
            color: #677d86;
            line-height: 24px;
          }
          .download {
            display: flex;
            align-items: center;
            font-size: 16px;
            font-weight: 400;
            color: #2478ff;
            line-height: 24px;
            cursor: pointer;
          }
        }
        .work {
          margin-left: 51px;
          margin-right: 40px;
          display: flex;
          justify-content: space-between;
          align-items: center;
          margin-top: 37px;
        }
        .work .question {
          font-size: 14px;
          font-weight: 500;
          color: #333330;
          line-height: 18px;
        }
        .work .active {
          width: 82px;
          height: 28px;
          background: linear-gradient(90deg, #a5d4e0 0%, #b4dce6 100%);
          border-radius: 4px;
          font-size: 14px;
          font-weight: 500;
          color: #ffffff;
          line-height: 24px;
          display: flex;
          align-items: center;
          justify-content: center;
          cursor: pointer;
          margin-right: 11px;
        }
        .work .unactive {
          width: 80px;
          height: 26px;
          border: 1px solid #a5d4e0;
          border-radius: 4px;
          font-size: 14px;
          font-weight: 500;
          color: #a5d4e0;
          line-height: 24px;
          display: flex;
          align-items: center;
          justify-content: center;
          margin-right: 11px;
          cursor: pointer;
        }
        .work .btncolor {
          background: linear-gradient(90deg, #84aad2 0%, #a4c5e9 100%);
        }
        .work .bordercolor {
          border: 1px solid #85aad2;
        }
        .work .fontcolor {
          color: rgba(133, 170, 210, 1);
        }
        .work .submit {
          width: 126px;
          height: 46px;
          background: #2478ff;
          box-shadow: 0px 1px 8px 0px rgba(56, 125, 247, 0.7);
          border-radius: 4px;
          font-size: 16px;
          font-weight: 800;
          color: #ffffff;
          line-height: 24px;
          display: flex;
          align-items: center;
          justify-content: center;
          cursor: pointer;
        }
      }
    }
    .teacher {
      width: 434px;
      height: 438px;
      // min-height: 557px;
      background-color: rgba(255, 255, 255, 1);
      border-radius: 8px;
      background: linear-gradient(
        180deg,
        rgba(36, 120, 255, 0.15) 0%,
        rgba(255, 255, 255) 50%
      );
      .title {
        display: flex;
        align-items: center;
        padding-top: 39px;
        position: relative;
        margin-left: 48px;
      }
      .title .text {
        margin-left: 8px;
        font-size: 16px;
        color: rgba(51, 51, 51, 1);
        font-weight: 800;
      }
      .title .box {
        width: 75px;
        height: 10px;
        background-color: rgba(36, 120, 255, 0.15);
        position: absolute;
        left: 23px;
        top: 53px;
      }
      .content {
        margin: 25px 24px 49px 49px;
        color: #677d86;
        width: 361px;
        height: 304px;
        line-height: 24px;
        font-size: 16px;
        font-weight: bold;
        font-family: PingFang-SC-Heavy;
      }
    }
  }
}
</style>
