<template lang="">
  <div>
    <footer><h1>{{ title }}</h1></footer>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: "Giá trị default",
    },
  },
  name: "comp-footer",
  data() {
    return {};
  },
};
</script>
<style lang="">
</style>
