<template>
  <div id="app">
    <div class="header">Header</div>
    <div class="content">
      <div class="boxes">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
        <img class="box" alt="Vue logo" src="./assets/logo.png">
      </div>
      <button v-on:click="moveUs">Move Us</button>
    </div>
    <div class="footer">Footer</div>
    
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" txt="boss" /> -->
    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import { gsap } from "gsap";

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  methods: {
    moveIt: function () {
      gsap.from(".header", {y: -100, duration: 1});
      gsap.from(".footer", {y: 100, duration: 1, delay: 1});
      gsap.from(".content", {opacity: 0, duration: 1, delay: 2, ease: "back.in", onComplete: this.moveUs});
    },
    moveUs: function () {
      gsap.to(".box", {rotation: "+=45", duration: 1, stagger: 0.1});
    }
  },
  mounted: function () {
    this.moveIt()
  }
}
</script>

<style>
body {
  margin: 0;
}
#app {
  height: 100vh;
  background-color: #a9bed3;
  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: space-between;
  overflow: hidden;
}
.header {
  background-color: #000;
  color: #fff;
  padding: 20px;
}
.footer {
  background-color: #000;
  color: #fff;
  padding: 20px;
}
.content {
  background-color: rgb(225, 228, 181);
  flex-grow: 2;
}
</style>
