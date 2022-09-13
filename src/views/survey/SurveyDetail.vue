<template>
  <div class="surveydetail">
    <!-- 面包屑导航 -->
    <div
      style="display: flex; align-items: center; justify-content: space-between"
    >
      <div class="crumb">
        <div>混合制项目</div>
        <div style="margin-left: 6px; margin-right: 6px">/</div>
        <div>管理者进阶-腾飞班</div>
        <div style="margin-left: 6px; margin-right: 6px">/</div>
        <div style="font-weight: 700; font-size: 16px">调研详情</div>
      </div>
      <div class="prevnext">
        <div class="prev">
          <img
            style="width: 23px; height: 23px"
            src="../../assets/image/prev.png"
          />
          <div style="margin-left: 7px">上一个</div>
        </div>
        <div class="prev" style="margin-left: 31px">
          <div style="margin-right: 7px">下一个</div>
          <img
            style="width: 23px; height: 23px"
            src="../../assets/image/next.png"
          />
        </div>
      </div>
    </div>
    <!-- 面包屑导航 -->
    <!-- 标题 -->
    <div class="title">【调研】管理者进阶腾飞班 - 培训阶段性调研</div>
    <!-- 标题 -->
    <!-- 基本信息 -->
    <div class="bascinfo">
      <div>
        <div
          class="question"
          v-for="(value, index) in question"
          :key="index"
          :style="{ 'margin-top': index === 0 ? '57px' : '41px' }"
        >
          <div class="text">{{ value.text }}</div>
          <div class="answer">
            <div class="answerL">完全没用</div>
            <div class="answerC">
              <div
                class="answerCitem"
                v-for="(item, key) in select"
                :key="key"
                :style="{
                  'margin-left': key === 0 ? '15px' : '10px',
                  background:
                    value.selectAnswer === item
                      ? 'rgba(86, 163, 249, 1)'
                      : 'rgba(86, 163, 249, 0)',
                  color:
                    value.selectAnswer === item
                      ? '#fff'
                      : 'rgba(86, 163, 249, 1)',
                }"
                @click="score(value, item)"
              >
                <div>{{ item }}</div>
              </div>
            </div>
            <div class="answerR">非常有帮助/启发</div>
          </div>
        </div>
        <div class="question" style="margin-top: 41px">
          <div class="text">4.类似相应的课程，您认为适合哪些人观看？</div>
          <div
            v-for="(value, index) in viewpeople"
            :key="index"
            style="display: flex; align-items: center"
            :style="{ 'margin-top': index === 0 ? '29px' : '22px' }"
            @click="selectPeople(value)"
          >
            <img
              style="width: 19px; height: 18px; cursor: pointer"
              :src="
                value.select
                  ? require('../../assets/image/checkbox.png')
                  : require('../../assets/image/checkbox2.png')
              "
            />
            <div class="people">{{ value.text }}</div>
          </div>
        </div>
        <div class="question" style="margin-top: 41px">
          <div class="text">5.您的其他意见</div>
          <div style="width: 713px; margin-top: 31px; position: relative">
            <el-input
              v-model="textarea1"
              :autosize="{ minRows: 5, maxRows: 5 }"
              resize="none"
              maxlength="200"
              type="textarea"
              @input="textareaInput"
            />
            <div class="words">{{ textarealength }}/200</div>
          </div>
        </div>
        <div style="display: flex; justify-content: center">
          <div class="submit">提交</div>
        </div>
      </div>
    </div>
    <!-- 基本信息 -->
  </div>
</template>
<script>
import { reactive, toRefs } from "vue";
export default {
  name: "SurveyDetail",
  setup() {
    const state = reactive({
      question: [
        {
          id: 1,
          text: "1.您觉得课程对您是否有用？",
          selectAnswer: 0,
        },
        {
          id: 2,
          text: "2.您是否会推荐课程给其他同事？",
          selectAnswer: 0,
        },
        {
          id: 3,
          text: "3.后续该讲师有其他课程是否会参与？",
          selectAnswer: 0,
        },
      ],
      select: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      viewpeople: [
        {
          id: 1,
          text: "基础员工",
          select: false,
        },
        {
          id: 2,
          text: "中层管理",
          select: false,
        },
        {
          id: 3,
          text: "专业人员",
          select: false,
        },
        {
          id: 4,
          text: "高级管理",
          select: false,
        },
      ],
      textarea1: "",
      textarealength: 0,
    });
    const score = (value, item) => {
      let arr = state.question;
      arr.map((i) => {
        if (i.id === value.id) {
          i.selectAnswer = item;
        }
      });
      state.question = arr;
    };
    const selectPeople = (value) => {
      let arr = state.viewpeople;
      arr.map((i) => {
        if (i.id === value.id) {
          i.select = !i.select;
        }
      });
      state.viewpeople = arr;
    };
    const textareaInput = (e) => {
      // console.log("eee", e);
      state.textarea1 = e;
      state.textarealength = e.length;
    };
    return {
      ...toRefs(state),
      score,
      selectPeople,
      textareaInput,
    };
  },
};
</script>
<style lang="scss">
.surveydetail {
  .crumb {
    color: #fff;
    display: flex;
    font-size: 14px;
    line-height: 24px;
  }
  .prevnext {
    display: flex;
    align-items: center;
    font-size: 14px;
    font-weight: 500;
    color: #ffffff;
    .prev {
      display: flex;
      align-items: center;
      cursor: pointer;
    }
  }
  .title {
    font-size: 20px;
    font-weight: 800;
    color: #ffffff;
    line-height: 24px;
    margin-top: 17px;
    margin-left: -11px;
  }
  .bascinfo {
    width: 100%;
    min-height: 1032px;
    margin-top: 24px;
    background: #ffffff;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    align-items: center;

    .question .text {
      font-size: 16px;
      font-weight: 500;
      color: #333330;
    }
    .question .answer {
      margin-top: 30px;
      display: flex;
      align-items: center;
      font-size: 14px;
      font-weight: 500;
      color: #56a3f9;
    }
    .question .answer .answerC {
      width: 540px;
      height: 73px;
      border: 1px solid #d7e5fd;
      border-radius: 8px;
      display: flex;
      align-items: center;
      margin-left: 11px;
      margin-right: 11px;
      // justify-content: center;
      .answerCitem {
        width: 40px;
        height: 40px;
        border: 1px solid #56a3f9;
        border-radius: 8px;
        font-size: 14px;
        font-weight: 400;
        color: #ffffff;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: 10px;
        cursor: pointer;
      }
    }
    .question .people {
      font-size: 14px;
      font-weight: 500;
      color: #333330;
      margin-left: 15px;
    }
    .question .words {
      position: absolute;
      right: 15px;
      bottom: 5px;
      font-size: 14px;
      font-weight: 500;
      color: #333330;
    }
    .question .el-textarea__inner {
      border-radius: 8px;
      background-color: rgba(245, 246, 247, 1);
    }
    .submit {
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
      margin-top: 39px;
      margin-bottom: 30px;
    }
  }
}
</style>
