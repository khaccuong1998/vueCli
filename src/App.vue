<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <button v-on:click="changeTitles()">Nhấp để đổi title</button>
    <comp-header
      v-bind:title="title"
      v-on:changeTitle="handleChangeTitle($event)"
    />
    <list-user
      v-bind:listUser="listUser"
      v-on:listUserDelete="listUserDelete($event)"
    />
    <comp-footer v-bind:title="title" />
    <demo-ref />
    <demo-slot />
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader";
import CompFooter from "./components/CompFooter";
import ListUser from "./components/ListUser";
import DemoRef from "./components/DemoRef";
import DemoSlot from "./components/DemoSlot.vue";
export default {
  name: "app",
  data() {
    return {
      title: "This is a header",
      listUser: [
        {
          id: 1,
          email: "KhacCuong@gmail.com",
          name: "cuong",
          active: true,
        },
        {
          id: 2,
          email: "KhacCuong1@gmail.com",
          name: "cuong1",
          active: true,
        },
        {
          id: 3,
          email: "KhacCuong2@gmail.com",
          name: "cuong2",
          active: true,
        },
        {
          id: 4,
          email: "KhacCuong3@gmail.com",
          name: "cuong3",
          active: false,
        },
        {
          id: 5,
          email: "KhacCuong4@gmail.com",
          name: "cuong4",
          active: true,
        },
      ],
    };
  },
  methods: {
    handleChangeTitle(d) {
      this.title = d.title;
      console.log("Viết trong App.vue", d);
    },
    listUserDelete(e) {
      var idxDelete = -1;
      this.listUser.forEach((u, index) => {
        console.log(
          "%cApp.vue line:68 object",
          "color: #007acc;",
          u.id,
          e.id,
          index
        );
        if (u.id == e.id) {
          idxDelete = index;
        }
      });
      console.log(
        "%cHello App.vue line:66 Đây là App.vue",
        "background: green; color: white; display: block;",
        idxDelete
      );
      if (idxDelete != -1) {
        this.listUser.splice(idxDelete, 1);
      }
    },
  },
  components: {
    CompHeader,
    CompFooter,
    ListUser,
    DemoRef,
    DemoSlot,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
