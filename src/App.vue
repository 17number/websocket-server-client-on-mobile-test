<template>
  <div id="app"></div>
</template>

<script>
// TODO: 上手く動作しない
import * as WebSocketServer from "ws/lib/websocket-server";
// import * as WebSocketServer from "isomorphic-ws/lib/websocket-server";
// const WebSocket = require('isomorphic-ws');
const wss = new WebSocketServer({ port: 8888 });

export default {
  name: "app",
  mounted() {
    console.log({ WebSocketServer: WebSocketServer, wss: wss });
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
