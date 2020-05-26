<template>
  <div id="app">
    <h1>WebRTC video call</h1>
    <h3>Room</h3>
    <input v-model="roomId"> 
    <button type="button" class="btn btn-primary" @click="onJoin">Join</button>
    <button type="button" class="btn btn-primary" @click="onLeave">Leave</button>
    <vue-webrtc ref="webrtc" width="100%" :roomId="roomId" :cameraHeight="400" :socketURL="'http://localhost:9002/'"/>
  </div>
</template>

<script>
import Vue from 'vue'
import WebRTC from 'vue-webrtc'

// ISSUE 5: https://github.com/westonsoftware/vue-webrtc/issues/5
import * as io from 'socket.io-client'
window.io = io
//
Vue.use(WebRTC)
export default {
  name: 'App',
  data() {
      return {
        roomId: "test-room"
      };
    },
  methods: {
    onJoin(){
        this.$refs.webrtc.join();
      },
    onShareScreen(){
        this.$refs.webrtc.shareScreen();
      },
    onLeave(){
        this.$refs.webrtc.leave();
      }
  }
  // mounted: function () {
  //   this.$refs.webrtc.join()
  // }
}
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