<template lang="">
  <div class="list-user">
   <User v-for="(user, index) in listUser" :key="index" v-bind:user="user" v-on:deleteUser="deleteUser($event)"/>
  </div>
</template>
<script>
import User from "./User";
export default {
  props: {
    listUser: {
      type: Array,
      default: null,
    },
  },

  name: "list-user",

  data() {
    return {};
  },
  components: {
    User,
  },
  methods: {
    deleteUser(e) {
      console.log(
        "%cListUser.vue line:26 ",
        "color: #26bfa5;",
        "Trong list User"
      );
      this.$emit("listUserDelete", e);
    },
  },
};
</script>
<style lang="">
.list-user {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.list-user .user {
  padding: 30px;
  margin-bottom: 30px;
  border: 1px solid black;
  width: calc(33.33333%-20px);
}
</style>
