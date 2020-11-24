<template>
  <div id="app" v-bind:style="styleObject">
    <img alt="Vue logo" src="./assets/logo.png" />
    <button @click="togglePalette()">
      {{ this.styleObject.background === "darkgray" ? "light" : "dark" }}
    </button>
    <HelloWorld msg="Hello there..!" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import HelloWorld from "./components/HelloWorld.vue";

export default Vue.extend({
  name: "App",
  components: {
    HelloWorld,
  },
  data: () => {
    return {
      styleObject: {
        background: "darkgray",
        color: "white",
      },
    };
  },
  methods: {
    togglePalette() {
      this.styleObject.background === "darkgray"
        ? (this.styleObject = {
            background: "white",
            color: "darkgray",
          })
        : (this.styleObject = {
            background: "darkgray",
            color: "white",
          });
    },
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  width: 100%;
}
</style>
