<template lang="">
  <div class="demoRef">
    <h1>Demo Ref</h1>
    <button class="avatar" v-on:click="handleFileInput($event)">Thay đổi avatar</button>
    <input type="file" style="display:none" ref="fileInputAvatar">
  </div>
</template>
<script>
export default {
  name: "demo-ref",
  data() {
    return {};
  },
  methods: {
    handleFileInput(e) {
      this.$refs.fileInputAvatar.click();
      // console.log(
      //   "%cHello DemoRef.vue line:16 ",
      //   "background: green; color: white; display: block;",

      // );
    },
  },
};
</script>
<style lang="">
.demoRef {
  margin-top: 100px;
  padding: 100px 30px;
  border: 1px solid #000;
}
.demoRef .avatar {
  color: #fff;
  border: 2px solid #333;
  padding: 12px 15px;
  background-color: #333;
  cursor: pointer;
  transition: all 0.3s ease;
}
.avatar:hover {
  color: #333;
  background-color: #fff;
}
</style>
