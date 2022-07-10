<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <DevPreview />
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";
import DevPreview from "@/components/DevPreview.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    DevPreview,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
