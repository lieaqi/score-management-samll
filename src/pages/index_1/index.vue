
<template>
  <section>
    <div class="top-bc">

    </div>
    <div class="user-card">
      <div>
        <image class="userImg" :src="userImg"></image>
        <div class="userName">落逸</div>
      </div>
    </div>
    <div>
      22
    </div>
  </section>
</template>

<script>
import userImg from "@/static/xiao.jpg";
export default {
  label: "",

  name: "",

  mixins: [],

  components: {},

  props: {},

  data() {
    return {
      userImg
    };
  },
  created() {},

  mounted() {},

  methods: {}
};
</script>
<style lang="scss" scoped>
.top-bc {
  background-color: #1772d6;
  height: 150upx;
  border-bottom-left-radius: 20upx;
  border-bottom-right-radius: 20upx;
}
.user-card {
  display: flex;
  justify-content: center;
  > div {
    background-color: white;
    width: 400upx;
    padding: 20upx;
    position: absolute;
    top: 40upx;
    border-radius: 20upx;
    display: flex;
    flex-direction: column;
    align-items: center;
    .userName{
    font-size: 34upx;
    margin-top: 10upx;
    }
   
    .userImg {
      width: 100upx;
      height: 100upx;
      border-radius: 50%;
    }
  }
}
</style>
