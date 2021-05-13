<template lang="">
  <div class="user" v-if="user.active">
    <button  class="delete" v-on:click="handleDelete()">Xoá user</button>
    <p>{{user.name}}</p>
    <p>{{user.email}}</p>
    <p>{{user.active}}</p>
    <br>
  </div>
</template>
<script>
export default {
  name: "user",
  props: {
    user: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {};
  },
  methods: {
    handleDelete() {
      var data = {
        id: this.user.id,
      };
      console.log(
        "%cUser.vue line:25 Object",
        "color: white; background-color: #007acc;",
        "Trong User.vue"
      );
      this.$emit("deleteUser", data);
      console.log("%cUser.vue line:24 object", "color: #007acc;", data);
    },
  },
};
</script>
<style lang="">
.user {
  position: relative;
}
.user .delete {
  position: absolute;
  top: 0;
  right: 0;
}
</style>
