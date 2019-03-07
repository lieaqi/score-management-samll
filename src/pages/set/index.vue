<template>
  <view class="content">
    <div class="c-flex top-user">
      <image class="userImg" :src="userImg"></image>
      <div class="flex-1 m-left-30 userInfo">
        <div class="main-text">落逸</div>
        <div class="tip-text">八年三班<span class="m-left-10">(2018)</span></div>
      </div>
    </div>
    <div class="padding-20-0"></div>
    <div class="flex-1 main">
      <view class="uni-list-cell" hover-class="uni-list-cell-hover">
        <view class="uni-list-cell-navigate uni-navigate-right">
          班级切换
        </view>

      </view>
      <view class="uni-list-cell" hover-class="uni-list-cell-hover">
        <view class="uni-list-cell-navigate uni-navigate-right">
          用户设置
        </view>

      </view>
    </div>

    <footer>
      <div class="tip-text ">落逸 2019</div>
    </footer>
  </view>
</template>

<script>
import userImg from "@/static/xiao.jpg";
export default {
  components: {},
  data() {
    return {
      userImg,
      latelyData: []
    };
  },
  onLoad() {},
  methods: {}
};
</script>

<style lang="scss" scoped>
.content {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.uni-list-cell {
  background-color: white;
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
.uni-list-cell::after{
   left: 0 !important
}
</style>
