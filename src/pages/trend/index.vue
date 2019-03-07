
<template>
  <section>
    <view class="canvasView">
      <div class="Lately-mess">
        平均分趋势
      </div>
      <div class="my-echarts">
        <mpvue-echarts :echarts="echarts" :onInit="lineInit" canvasId="line1" ref="lineChart" />
      </div>
      <div class="Lately-mess">
        排名趋势
      </div>
       <div class="my-echarts">
        <mpvue-echarts :echarts="echarts" :onInit="lineInit1" canvasId="line2" ref="lineChart" />
      </div>
    </view>
  </section>
</template>

<script>
import * as echarts from "@/static/echarts.simple.min.js";
import mpvueEcharts from "@/components/echarts.vue";
let lineOption1 = {
  animation: false,
  color: ["#37A2DA", "#9FE6B8"],
  grid: {
    x: 35,
    y: 30
  },
  calculable: false,
  xAxis: [
    {
      type: "category",
      data: ["入学", "9月", "期中", "11月", "12月", "期末"]
    }
  ],
  yAxis: [
    {
      type: "value",
      splitArea: {
        show: true
      }
    }
  ],
  series: [
    {
      name: "平均分",
      type: "line",
      data: [470, 480, 465, 477, 468, 488]
    }
  ]
};
let lineOption2 = {
  animation: false,
  color: ["#37A2DA", "#9FE6B8"],
  grid: {
    x: 35,
    y: 30
  },
  calculable: false,
  xAxis: [
    {
      type: "category",
      data: ["入学", "9月", "期中", "11月", "12月", "期末"]
    }
  ],
  yAxis: [
    {
      type: "value",
      splitArea: {
        show: true
      }
    }
  ],
  series: [
    {
      name: "排名",
      type: "line",
      data: [2, 3, 1, 2, 2, 1]
    }
  ]
};
export default {
  label: "",

  name: "",

  mixins: [],

  components: {
    mpvueEcharts
  },

  props: {},

  data() {
    return {
      echarts
    };
  },
  created() {},

  mounted() {},

  methods: {
    lineInit(canvas, width, height) {
      let lineChart = echarts.init(canvas, null, {
        width: width,
        height: height
      });
      canvas.setChart(lineChart);

      lineChart.setOption(lineOption1);
      return lineChart;
    },
    lineInit1(canvas, width, height) {
      let lineChart = echarts.init(canvas, null, {
        width: width,
        height: height
      });
      canvas.setChart(lineChart);

      lineChart.setOption(lineOption2);
      return lineChart;
    }
  }
};
</script>
<style lang="scss" scoped>
.my-echarts {
  height: 500upx;
}
.Lately-mess {
  background-color: white;
  padding: 20upx 40upx;
  box-shadow: 3upx 3upx 3upx #d5d5d6;
}
</style>
