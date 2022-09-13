<template>
  <div class="faceteach">
    <!-- 面包屑导航 -->
    <div class="crumb">
      <div>课程列表</div>
      <div style="margin-left: 6px; margin-right: 6px">/</div>
      <div style="font-weight: 700">课程详情</div>
    </div>
    <!-- 面包屑导航 -->

    <!-- 基本信息 -->
    <div class="bascinfo">
      <div style="margin-left: 46px">
        <div class="title">【其他活动】核心项目面授课</div>
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
              <div class="text">课程详情</div>
              <div class="box"></div>
            </div>
            <div style="display: flex; align-items: center">
              <div class="content">
                通过对各级人员的软件平台培训，使其能够了解如何运用乾元坤和智能信息管理系统来提升企业管理水平，最大限度发挥软件产品在企业中的作用。<br />
                1.使企业不同部门人员掌握便捷、有效的系统平台操作方法;<br />
                2.通过系统平台的培训提高员工对企业的管理理念认识与提升。<br />
                3.通过系统平台培训加强沟通，统一部署，协同工作，提高效率。<br />
              </div>
            </div>
          </div>
        </div>
        <div class="detailB">
          <el-tabs v-model="activeName" @tab-click="handleClick">
            <el-tab-pane label="课程附件" name="first">
              <div
                v-for="(el, index) in enclosure"
                :key="el.id"
                class="enclosure"
                :style="{
                  'border-bottom':
                    index === enclosure.length - 1
                      ? null
                      : '1px solid rgba(56, 125, 247, 0.2)',
                }"
              >
                <div class="enclosureL">
                  <img
                    style="width: 22px; height: 26px; margin-left: 10px"
                    :src="el.img"
                  />
                  <div style="margin-left: 20px">{{ el.name }}</div>
                </div>
                <div class="download">
                  <img
                    style="width: 16px; height: 15px"
                    src="../../assets/image/download.png"
                  />
                  <div style="margin-left: 5px">下载</div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="课程作业" name="second">
              <div class="work">
                <div>
                  <div class="question">社交产品如何做好模块化处理？</div>
                  <div style="margin-top: 16px; display: flex">
                    <div class="active">必修</div>
                    <div class="unactive">作业</div>
                  </div>
                </div>
                <div class="submit">提交</div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="课程考试" name="third">
              <div class="work">
                <div>
                  <div class="question">
                    模块化产品展示相关案例与展示：如何自由组合你的思考？
                  </div>
                  <div style="margin-top: 16px; display: flex">
                    <div class="active btncolor">必修</div>
                    <div class="unactive bordercolor fontcolor">考试</div>
                  </div>
                </div>
                <div class="submit">去考试</div>
              </div>
            </el-tab-pane>
          </el-tabs>
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
    <!-- 详细信息 -->
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "FaceTeach",
  setup() {
    const state = reactive({
      activeName: "first",
      enclosure: [
        {
          id: 1,
          name: "项目参考文档.doc",
          img: require("../../assets/image/file/word.png"),
        },
        {
          id: 2,
          name: "人工智能启蒙讲解讲义.pptx",
          img: require("../../assets/image/file/ppt.png"),
        },
        {
          id: 3,
          name: "人工智能启蒙讲解讲义.xlsx",
          img: require("../../assets/image/file/excel.png"),
        },
      ],
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
        {
          id: 3,
          name: "王星天（显示事业）",
          introduce:
            "教师是学生的镜子,学生是老师的影子。教师是学生的镜子,学生是老师的影子。教师是学生的镜子,学生是老师的影子。教师是学生的镜子,学生是老师的影子。",
          peopleimg: require("../../assets/image/img.jpg"),
          medal: [
            require("../../assets/image/medal/medal1.png"),
            require("../../assets/image/medal/medal2.png"),
            require("../../assets/image/medal/medal3.png"),
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
.faceteach {
  .crumb {
    color: #fff;
    display: flex;
    font-size: 14px;
    line-height: 24px;
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
        height: 263px;
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
      min-height: 557px;
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
}
</style>
