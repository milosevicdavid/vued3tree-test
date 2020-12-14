<template>
  <div id="app">
    <h2>Circle graph</h2>
    <div class="graph">
      <tree
        :data="cluster"
        node-text="name"
        layoutType="circular"
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
      cluster: {
        name: "JavaScript Frameworks",
        children: [
          {
            name: "Frontend",
            children: [
              { name: "Angular" },
              { name: "Vue.js" },
              { name: "React" },
              { name: "Svelte" },
            ],
          },
          {
            name: "Backend",
            children: [
              { name: "Express" },
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
  width: 650px;
  height: 650px;
}
</style>
