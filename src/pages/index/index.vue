<template>
  <view class="content">
    <div class="c-flex top-user">
      <image class="userImg" :src="userImg"></image>
      <div class="flex-1 m-left-30 userInfo">
        <div class="main-text">落逸</div>
        <div class="tip-text">八年三班<span class="m-left-10">(2018)</span></div>

        <i class="iconfont setting" @click="goSet">&#xe61d;</i>

      </div>
    </div>
    <div class="padding-10-0"></div>
    <div class="flex-1 main">
      <div class=" main-menu">
        <div class="flex-1" hover-class="main-btn-hover " @click="goTrend">
          成绩趋势
        </div>
        <div class="flex-1 " hover-class="main-btn-hover " @click="goExam">
          考试列表
        </div>
        <div class="flex-1 " hover-class="main-btn-hover " @click="goStudents">
          学生详情
        </div>
      </div>
      <div class="Lately-mess">
        最近考试
      </div>
      <view class="uni-card" v-for="(data,i) in latelyData" :key="i">
        <view class="uni-card-header">{{data.examName}}</view>
        <view class="uni-card-content">
          <view class="uni-card-content-inner">
            <div class="m-bottom-20">{{data.describe.rankSum}}</div>
            <div class="m-bottom-10">各科详情如下:</div>
            <div> {{data.describe.rank}}</div>
          </view>
        </view>
        <view class="uni-card-footer">{{data.date}}</view>
      </view>
    </div>

    <footer>
      <div class="tip-text ">落逸 2019</div>
    </footer>
  </view>
</template>

<script>
import userImg from "@/static/xiao.jpg";
import setting from "@/static/setting.png";
export default {
  components: {},
  data() {
    return {
      title: "Hello",
      userImg,
      latelyData: [],
      setting
    };
  },
  onLoad() {
   
    //let texts=["期末考试","12月月考","11月月考","期中考试","9月月考","入学考试"]
    let texts = ["期末考试"];
    texts.forEach(t => {
      this.latelyData.push({
        examName: t,
        date: "2019-03-07",
        describe: {
          rankSum: "本次考试全校排名第二,平均分为486。",
          rank:
            "数学:88(第一),英语:78(第二),语文:81(第二),政治:44(第四),历史:38(第四),物理:55(第一),化学:44(第一)。"
        }
      });
    });
  },
  methods: {
    goExam() {
      uni.navigateTo({
        url: "/pages/exams/index"
      });
    },
    goStudents() {
      uni.navigateTo({
        url: "/pages/students/index"
      });
    },
    goSet() {
      uni.navigateTo({
        url: "/pages/set/index"
      });
    },
    goTrend() {
      uni.navigateTo({
        url: "/pages/trend/index"
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.setting {
  position: absolute;
  right: 20upx;
  top: 30upx;
  font-size: 42upx;
}
.Lately-mess {
  background-color: white;
  padding: 20upx 40upx;
  box-shadow: 3upx 3upx 3upx #d5d5d6;
}
.uni-card {
  margin: 40upx;
  box-shadow: 0 5upx 26upx 0 #d5d5d6;
}
.content {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.main-menu {
  margin: 40upx;
  border-radius: 20upx;
  display: flex;
  height: 200upx;
  > .flex-1 {
    border-radius: 15upx;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
    box-shadow: 0 5upx 26upx 0 #d5d5d6;
  }
  .flex-1 + .flex-1 {
    margin-left: 20upx;
  }
}
.top-user {
  color: white;
  padding: 40upx;
  background-color: #297fdc;
  flex: 0 0 120upx;
  box-shadow: 0upx 5upx 5upx #297fdc;
  .userImg {
    width: 120upx;
    height: 120upx;
    border-radius: 50%;
  }
  .userInfo {
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    padding: 2upx 0;
  }
}
footer {
  padding: 16upx;
  text-align: center;
  color: #e1e1e1;
}
</style>
