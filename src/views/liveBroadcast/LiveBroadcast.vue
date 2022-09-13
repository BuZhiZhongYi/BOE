<template>
  <div class="moreactive">
    <!-- 面包屑导航 -->
    <div class="crumb">
      <div>混合制项目</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div>管理者进阶-腾飞班</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div style="font-weight: 700; font-size: 16px">直播详情</div>

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
        <div class="title">【直播】管理者进阶腾飞班 - 毕业典礼</div>
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
      <div
        class="btn"
        style="margin-right: -660px; background: rgb(59, 191, 252)"
      >
        观看
      </div>
      <div
        class="btn"
        style="margin-right: -660px; background: rgb(57, 146, 249)"
      >
        签到
      </div>
      <div class="btn">评估</div>
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
                src="../../assets/image/course.png"
              />
              <div class="text">课前预习</div>
              <div class="box"></div>
            </div>
            <div style="display: flex; align-items: center">
              <div class="content">
                通过对各级人员的软件平台培训，使其能够了解如何运用乾元坤和智能信息管理系统来提升企业管理水平，最大限度发挥软件产品在企业中的作用;<br />
                ● 培训目标
                <br />1.使企业不同部门人员掌握便捷、有效的系统平台操作方法;<br />
                2.通过系统平台的培训提高员工对企业的管理理念认识与提升。<br />
                3.通过系统平台培训加强沟通，统一部署，协同工作，提高效率。
                <br />
                ●培训对象<br />
                集团领导、各相关部门领导、总经理、车间主管、车间操作员等;<br />
              </div>
            </div>

            <div class="title">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/write.png"
              />
              <div class="text">课后作业</div>
              <div class="box"></div>
            </div>
            <div style="display: flex; align-items: center">
              <div class="content">
                <span style="font-weight: 600"
                  >网易有道词典现有功能结构拆解+问题分析</span
                ><br />
                查找资料，介绍一种国外（日本、美国、欧洲）道路（公路、铁路、城市道路、地铁）设计规范的演变过程，可以一种或几种主要技术指标为例，并说明其原因。<br />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div class="tell">
          <div class="title">
            <img
              style="width: 21px; height: 23px"
              src="../../assets/image/tv.png"
            />
            <div class="text">直播公告</div>
            <div class="box"></div>
          </div>
          <div class="content">
            当你走进这直播间，我和毛不易老师@毛不易就已
            经在直播间等你们了!今晚20点30，不见不散!<br />
          </div>
        </div>
        <div class="teacher">
          <div class="title">
            <img
              style="width: 21px; height: 23px"
              src="../../assets/image/livelecturer.png"
            />
            <div class="text">直播讲师</div>
            <div class="box"></div>
          </div>
          <div
            v-for="(el, index) in teacher"
            :key="el.id"
            class="teacheritem"
            :style="{
              'border-bottom':
                index === teacher.length - 1
                  ? null
                  : '1px solid rgba(56, 125, 247, 0.2)',
            }"
          >
            <img class="peopleimg" :src="el.peopleimg" />
            <div style="margin-left: 17px">
              <div class="teacherName">
                <div style="margin-right: 5px">{{ el.name }}</div>
                <div v-for="(item, key) in el.medal" :key="key">
                  <img class="teacherMedal" :src="item" />
                </div>
              </div>
              <div class="introduce">{{ el.introduce }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- 详细信息 -->
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "LiveBroadcast",
  setup() {
    const state = reactive({
      activeName: "first",
      teacher: [
        {
          id: 1,
          name: "王星天（显示事业）",
          introduce: "教师是学生的镜子,学生是老师的影子。",
          peopleimg: require("../../assets/image/img.jpg"),
          medal: [
            require("../../assets/image/medal/medal1.png"),
            require("../../assets/image/medal/medal2.png"),
            require("../../assets/image/medal/medal3.png"),
          ],
        },
        {
          id: 2,
          name: "王星天（显示事业）",
          introduce: "教师是学生的镜子,学生是老师的影子。",
          peopleimg: require("../../assets/image/img.jpg"),
          medal: [
            require("../../assets/image/medal/medal1.png"),
            require("../../assets/image/medal/medal2.png"),
          ],
        },
      ],
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
        height: 646px;
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
    .tell {
      width: 434px;
      height: 188px;
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
  .teacher {
    margin-top: 22px;
    width: 434px;
    height: 328px;
    background-color: rgba(255, 255, 255, 1);
    border-radius: 8px;
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
    .teacheritem {
      margin-left: 48px;
      margin-right: 48px;
      // min-height: 115px;
      padding: 25px 0px;
      display: flex;
      align-items: center;
    }
    .teacheritem .peopleimg {
      width: 60px;
      height: 60px;
      border-radius: 30px;
    }
    .teacheritem .teacherName {
      font-size: 14px;
      font-weight: bold;
      color: #394145;
      display: flex;
      align-items: center;
      width: 260px;
    }
    .teacheritem .teacherName .teacherMedal {
      width: 17px;
      height: 19px;
      margin-right: 4px;
      display: flex;
      align-items: center;
    }
    .teacheritem .introduce {
      width: 260px;
      font-size: 14px;
      font-weight: 500;
      color: #394145;
      margin-top: 14px;
    }
  }
}
</style>
