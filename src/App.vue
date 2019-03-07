<script>
export default {
  onLaunch: function() {
    console.log("App Launch");
  },
  onShow: function() {
     uni.showShareMenu({withShareTicket:true})
    console.log("App Show");
  },
  onHide: function() {
    console.log("App Hide");
  }
};
</script>

<style >
@import "./common/uni.css";
body {
  /* background: linear-gradient(#007aff, #07396f, #609ad8); */
  background: whitesmoke;
  
}
page {
  height: 100%;
}
uni-page-body {
  height: 100%;
  overflow: auto;
}
</style>
