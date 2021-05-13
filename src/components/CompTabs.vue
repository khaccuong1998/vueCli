<template lang="">
  <div class="comp-tabs">
    <div class="tabs-title">
      <span class="">{{ title }}</span>
      <ion-icon name="heart"></ion-icon>
    </div>
    <div class="tabs-content">
        <slot></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "comp-tabs",
  props: {
    title: String,
  },
  data() {
    return {};
  },
};
</script>
<style lang="">
.tabs-title {
  padding: 12px 20px;
  display: flex;
  justify-content: space-between;
  border: 1px solid black;
}
.tabs-header {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}
.tabs-content {
  margin-top: 2px;
  padding: 12px;
  border: 2px solid rgb(25, 60, 156);
  text-align: left;
}
.tabs-header li {
  padding: 8px 12px;
  background-color: #ccc;
  transition: all 0.5s ease;
}
.tabs-header li:hover {
  color: #fff;
  background-color: #333;
  cursor: pointer;
}
.tabs-header .active {
  color: #fff;
  background-color: #333;
  cursor: pointer;
}
</style>
