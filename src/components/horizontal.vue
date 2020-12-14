<template>
  <div id="app">
    <h2>Horizontal graph</h2>
    <div class="graph">
      <tree
        :data="tree"
        node-text="name"
        layoutType="horizontal"
        :duration="100"
      >
      </tree>
    </div>
  </div>
</template>

<script>
import { tree } from "vued3tree";

export default {
  name: "App",
  components: {
    tree,
  },

  data() {
    return {
      tree: {
        name: "JavaScript Frameworks",
        children: [
          {
            name: "Frontend Frameworks",
            children: [
              { name: "Angular" },
              { name: "Vue.js" },
              { name: "React" },
              { name: "Svelte" },
            ],
          },
          {
            name: "Backend Frameworks",
            children: [
              {
                name: "Express",
              },
              { name: "Koa" },
              { name: "Meteor" },
              { name: "Sails" },
            ],
          },
        ],
      },
    };
  },
};
</script>

<style>
h2 {
  text-align: center;
}

.graph {
  width: 700px;
  height: 700px;
}
</style>
