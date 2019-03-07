
<template>
  <view class="main">
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
  </view>
</template>

<script>
import uniBadge from "@/components/uni-badge.vue";
export default {
  label: "",

  name: "",

  mixins: [],

  components: {
    uniBadge
  },

  props: {},

  data() {
    return {
      latelyData: []
    };
  },
  created() {
    this.getLatelyData();
  },
  onLoad() {},

  mounted() {},

  methods: {
    getLatelyData() {
      let texts = [
        "期末考试",
        "12月月考",
        "11月月考",
        "期中考试",
        "9月月考",
        "入学考试"
      ];
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
    }
  }
};
</script>
<style lang="scss" scoped>
.main {
  padding: 40upx;
}
</style>
