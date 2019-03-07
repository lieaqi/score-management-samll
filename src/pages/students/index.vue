
<template>
  <section>
    <div v-for="i in 20" :key="i">
      <view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(value,key) in list" :key="key">
        <view class="uni-list-cell-navigate uni-navigate-right uni-media-list ">
          <view class="uni-media-list-logo">
            <image :src="value.img"></image>
          </view>
          <view class="uni-media-list-body">
            <view class="uni-media-list-text-top">{{value.studentName}}</view>
            <view class="uni-media-list-text-bottom uni-ellipsis">{{value.address}}</view>
          </view>
        </view>
      </view>
    </div>
  </section>
</template>

<script>
export default {
  label: "学生详情",

  name: "students",

  mixins: [],

  components: {},

  props: {},

  data() {
    return {
      list: [
        {
          studentName: "张三",
          address: "浙江省温州市鹿城区",
          img:
            "https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/shuijiao.jpg?imageView2/3/w/200/h/100/q/90"
        },
        {
          studentName: "李四",
          address: "浙江省温州市瓯海区",
          img:
            "https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/muwu.jpg?imageView2/3/w/200/h/100/q/90"
        },
        {
          studentName: "王五",
          address: "浙江省温州市龙湾区",
          img:
            "https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/cbd.jpg?imageView2/3/w/200/h/100/q/90"
        }
      ]
    };
  },
  created() {},

  mounted() {},

  methods: {}
};
</script>
<style lang="scss" scoped>
section {
  background-color: white;
}
</style>
