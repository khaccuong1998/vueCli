<template lang="">
  <div class="demo-slot">
    <comp-tabs title="Tiêu đề của tabs">
      <ul class="tabs-header">
        <li v-for="(item, index) in tabsHeader" :key="index" v-on:click="handleClick(index)"
          v-bind:class="{active:isActive(index)}">
          {{item.text}}</li>
      </ul>
      <div class="tabs-content tab1" v-if="tabActive===0">
        <p>Tab1 Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa laborum aperiam suscipit fugit
          temporibus,
          provident fuga rem reprehenderit corrupti, amet soluta consequatur odit non dignissimos velit nostrum
          laudantium asperiores! A.</p>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consequuntur repudiandae, assumenda voluptas nobis
          vel, minima dolores explicabo tenetur quibusdam ipsa perspiciatis rerum impedit ex veritatis aut vitae ullam
          nam dignissimos.</p>
      </div>
      <div class="tabs-content tab2" v-if="tabActive===1">
        <p>Tab2 Lorem ipsum dolor sit amet consectetur, adipisicing elit. Atque vitae minus esse ullam mollitia laborum
          non qui placeat enim nesciunt. Dolor nostrum illo perferendis distinctio reiciendis commodi sed voluptatem
          rerum?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate, officiis? Non doloremque beatae, in ipsam
          quo repellendus nostrum iste necessitatibus quisquam ratione ducimus saepe labore? Nemo rem vel cum deserunt!
        </p>
      </div>
      <div class="tabs-content tab3" v-if="tabActive===2">
        <p>Tab3 Lorem ipsum dolor sit amet consectetur adipisicing elit. Similique reprehenderit eius at atque officia
          ducimus esse id veritatis rerum. Veritatis amet iure autem quisquam voluptates eligendi aliquid repellat fuga
          laborum?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem tempore, iste alias accusamus animi suscipit!
          Natus impedit optio ad fugit laborum? Maxime eveniet quia sint expedita officia cumque fuga consectetur.</p>
      </div>

    </comp-tabs>
  </div>
</template>
<script>
  import CompTabs from "./CompTabs";
  export default {
    name: "demo-slot",
    data() {
      return {
        tabsHeader: [
          { text: "tab1" }, { text: "tab2" }, { text: "tab3" }
        ],
        tabActive: 0
      };

    },
    methods: {
      handleClick(index) {
        this.tabActive = index;
      },
      isActive(index) {
        if (this.tabActive == index) {
          return true;
        } else return false;
      }
    },
    components: {
      CompTabs,
    },
  };
</script>
<style lang="">
  .demo-slot {
    margin-top: 100px;
    padding: 100px 30px;
    border: 1px solid #000;
  }
</style>
