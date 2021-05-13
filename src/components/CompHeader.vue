<template lang="">
    <div>
        <header><h1>{{ title }}</h1><br><button v-on:click="changeTitleEv()">Thay đổi title header</button></header>
    </div>
</template>
<script>
export default {
  name: "comp-header",
  props: {
    title: String,
  },
  data() {
    return {};
  },
  methods: {
    changeTitleEv() {
      var dataTitle = {
        title: "Cái này là text trong data",
      };
      console.log("CompHeader.vue");
      this.$emit("changeTitle", dataTitle);
      console.log("Sau khi chạy emit");
    },
  },
};
</script>
<style lang="">
</style>
