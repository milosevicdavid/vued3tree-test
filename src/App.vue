<template>
  <div id="App">
    <h1>David's vued3tree library testing</h1>
    <div class="buttons">
      <button @click="view = 'horizontal-graph'">Horizontal</button>
      <button @click="view = 'circle-graph'">Circle</button>
    </div>
    <div class="component">
      <transition name="component-fade" mode="out-in">
        <component :is="view"> </component>
      </transition>
    </div>
  </div>
</template>

<script>
import Horizontal from "./components/horizontal.vue";
import Circle from "./components/circle.vue";

export default {
  data() {
    return {
      view: "horizontal-graph",
    };
  },

  components: {
    "circle-graph": Circle,
    "horizontal-graph": Horizontal,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Oswald&display=swap");

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


#App {
  font-family: "Oswald", sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}

.component {
  display: block;
}

.component-fade-enter-active,
.component-fade-leave-active {
  transition: opacity 0.3s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

h1 {
  background-color: black;
  padding-top: 20px;
  padding-bottom: 20px;
  color: white;
  width: 100%;
  text-align: center;
  word-spacing: 10px;
}

button {
  background-color: black;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  cursor: pointer;
  margin-right: 20px;
  outline: none;
  border: 1px solid black;

  &:hover {
    background-color: white;
    color: black;
    border: 1px solid black;
    border-radius: 0;
  }
}
</style>
