<template>
  <div class="moreactive">
    <!-- 面包屑导航 -->
    <div class="crumb">
      <div>混合制项目</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div>管理者进阶-腾飞班</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div style="font-weight: 700; font-size: 16px">投票详情</div>

      <div class="preNext">
        <button class="btn btn01"></button>
        <span class="content">上一个</span>
        <span class="content" style="margin-left: 31px">下一个</span>
        <button class="btn btn02"></button>
      </div>
    </div>
    <!-- 面包屑导航 -->
    <div class="debateTitle">【投票】管理者进阶腾飞班 - 授课方式</div>
    <!-- 详细信息 -->
    <div class="detailinfo">
      <div class="detail">
        <div class="detailT">
          <div style="margin-left: 48px; margin-right: 48px">
            <div class="title">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/yuan.png"
              />
              <div class="text">参与情况</div>
              <div class="box"></div>
            </div>
            <!-- <div style="display: flex; align-items: center"></div> -->
            <div class="all">
              <div class="item allbox1">
                <div class="item1" style="color: #089dff">123</div>
                <div class="item2">参与数</div>
              </div>
              <div class="item allbox2">
                <div class="item1" style="color: #387df7">6172</div>
                <div class="item2">总票数</div>
              </div>
              <div class="item allbox3">
                <div class="item1" style="color: #00c6ff">11241</div>
                <div class="item2">浏览数</div>
              </div>
            </div>

            <div class="title">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/yuan.png"
              />
              <div class="text">参与投票</div>
              <div class="box"></div>
            </div>

            <div class="join"></div>
          </div>
          <div class="right">
            <div class="righttitle">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/yuan.png"
              />
              <div class="text">投票时间</div>
              <div class="box"></div>
            </div>
            <div class="timebox clearfix">
              <div class="innertime">
                2022-7-20
                00:00&nbsp;&nbsp;&nbsp;&nbsp;至&nbsp;&nbsp;&nbsp;&nbsp;2022-8-29
                23:59:59
              </div>
              <div class="endtime clearfix">
                <div class="endtimetext">
                  距离结束还有&nbsp;&nbsp;
                  <span class="te">123</span>&nbsp;&nbsp; 小时&nbsp;&nbsp;<span
                    class="te"
                    >42</span
                  >&nbsp;&nbsp;分钟
                </div>
              </div>
            </div>
            <div class="righttitle">
              <img
                width="20px"
                height="20px"
                src="../../assets/image/yuan.png"
              />
              <div class="text">投票说明</div>
              <div class="box"></div>
            </div>
            <div class="explain clearfix">
              <div class="explaincontent">
                为提高核心项目讲解体验，现向广大学员征集较为接受的授课方式,每位学员可投票2个选项，我们将选取最高选项的两个做后续讲解。
              </div>
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
  name: "balloT",
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

  .debateTitle {
    margin-top: 15px;
    font-size: 20px;
    line-height: 24px;
    height: 24px;
    font-weight: 600;
  }

  .detailinfo {
    width: calc(100% + 20px);
    margin-top: 20px;
    display: flex;
    .detail {
      flex: 1;
      margin-right: 20px;
      .detailT {
        height: 1000px;
        background: #ffffff;
        border-radius: 8px;
        color: rgba(51, 51, 51, 1);
        display: flex;

        .right {
          .righttitle {
            display: flex;
            padding-top: 39px;
            position: relative;
            .text {
              margin-left: 8px;
              font-size: 16px;
              color: rgba(51, 51, 51, 1);
              font-weight: 800;
            }
            .box {
              width: 75px;
              height: 10px;
              background-color: rgba(36, 120, 255, 0.15);
              position: absolute;
              left: 23px;
              top: 53px;
            }
          }
          .timebox {
            width: 417px;
            height: 149px;
            background: linear-gradient(90deg, #b6c6e1 0%, #89aed6 100%);
            border-radius: 4px;
            margin-top: 42px;
          }
          .clearfix:before,
          .clearfix:after {
            content: "";
            display: table;
            clear: both;
          }
          .innertime {
            margin-top: 17px;
            margin-left: 55px;
            font-size: 14px;
            font-family: PingFang SC;
            font-weight: 500;
            color: #ffffff;
            line-height: 24px;
          }
          .endtime {
            margin-left: 10px;
            margin-top: 16px;
            width: 397px;
            height: 81px;
            background: #f2f5f7;
            border-radius: 0px 8px 0px 8px;
            .endtimetext {
              margin-top: 25px;
              margin-left: 46px;
              .te {
                font-size: 28px;
                font-family: PingFang SC;
                font-weight: 800;
                color: #4a9cf8;
                line-height: 24px;
              }
            }
          }
          .explain {
            margin-top: 30px;
            width: 416px;
            height: 158px;
            background: #f2f5f7;
            border-radius: 8px;
          }
          .explaincontent {
            width: 368px;
            height: 64px;
            font-size: 16px;
            font-family: PingFang SC;
            font-weight: 500;
            color: #333330;
            line-height: 24px;
            margin-left: 24px;
            margin-top: 47px;
          }
        }

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
        .all {
          display: flex;
          justify-content: space-between;
          width: 1280px;
          margin-top: 43px;
          .allbox1 {
            background: linear-gradient(
              0deg,
              rgba(160, 193, 230, 0) 0%,
              rgba(161, 195, 231, 0.2) 100%
            );
          }
          .allbox2 {
            background: linear-gradient(
              0deg,
              rgba(177, 219, 229, 0) 0%,
              rgba(172, 216, 227, 0.2) 100%
            );
          }
          .allbox3 {
            background: linear-gradient(
              0deg,
              rgba(195, 209, 234, 0) 0%,
              rgba(191, 206, 231, 0.2) 100%
            );
          }
          .item {
            width: 410px;
            height: 149px;
            text-align: center;
            border-radius: 4px;
            .item1 {
              color: #089dff;
              font-size: 24px;
              font-weight: bold;
              margin-top: 36px;
            }
            .item2 {
              color: #333330;
              font-size: 14px;
              margin-top: 29px;
            }
          }
        }
        .join {
          width: 1280px;
          height: 408px;
          background: #f5f6f7;
          border-radius: 8px;
          margin-top: 32px;
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
  }
}
</style>
