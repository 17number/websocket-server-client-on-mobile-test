<template>
  <div id="app" v-if="deviceready">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  data() {
    return {
      deviceready: false
    };
  },
  methods: {
    onDeviceReady() {
      console.log("device ready");
      this.deviceready = true;
    },
    isMobile() {
      const ua = navigator.userAgent.toLowerCase();
      return (
        ua.includes("iphone") || ua.includes("ipad") || ua.includes("android")
      );
    }
  },
  created() {
    if (this.isMobile()) {
      console.log("mobile");
      document.addEventListener("deviceready", this.onDeviceReady, false);
    } else {
      console.log("not mobile");
      this.deviceready = true;
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
