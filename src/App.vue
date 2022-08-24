<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld ref="hello" msg="Welcome to Your Vue.js App" />
  <header-app ref="header" />
  <button @click="changeEvent">Test event</button>
</template>

<script>
import HeaderApp from "./components/HeaderApp.vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    HeaderApp,
  },
  methods: {
    changeEvent() {
      // this.$refs.hello.onConsoleLogTesting();
      // console.log("Running here...");
      console.log(this.$refs.hello);
      console.log(this.$refs.header);
    },
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
