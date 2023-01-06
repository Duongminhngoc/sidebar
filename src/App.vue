<template>
  <div id="app">
    <div class="app">
      <div class="zap-sliderout">
        <h2>&lt;zap-slideout&gt;</h2>
        <p>Give it a jolt. Click <span>Open</span>at the top.</p>
      </div>
    </div>

    <div class="sidebar" :class="{'div-close': isClose}">
      <ul>
        <li>
          <img class="zap-emoji" src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/19332/zap-emoji.svg" alt="Zap Emoji"/>
        </li>
        <li class="nav-first"><a href="#">Home</a></li>
        <li class="nav-first"><a href="#">Work</a></li>
        <li class="nav-first"><a href="#">Contact</a></li>
        <li class="nav-last"><a href="#">Tip</a></li>
        <li class="nav-last"><a href="#">Resource</a></li>
        <li class="nav-last"><a href="#">Shenanigans</a></li>
        <li class="close" @click="closeHandle">{{text}}</li>
      </ul>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isClose: false,
      text: "Close",
    };
  },
  methods: {
    closeHandle() {
      this.isClose = !this.isClose
      if (this.isClose === false) {
        this.text = 'Close'
      } else {
        this.text = 'Open'
      }
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #ffffff;
  background-color: #2c3e50;
}
.app {
  position: relative;
  text-align: center;
  height: 100vh;
}
.zap-sliderout {
  position: absolute;
  top: 50%;
  width: 100%;
  text-align: center;
}
.zap-sliderout p {
  margin-top: 20px;
}
.sidebar {
  position: absolute;
  box-sizing: border-box;
  top: 0;
  width: 250px;
  height: 100%;
  background-color: #34495E;
  transition: all .4s ease-in-out;
}
.sidebar h1 {
  font-size: 50px;
}
ul {
  list-style:none;
  position: relative;
  padding: 50px 30px;
}
ul li.nav-first{
  font-size: 40px;
  font-weight: bold;
}
ul li.nav-first a:hover{
  border-bottom: 0.1em white solid;
}
ul li.nav-last{
  font-size: 20px;
  text-transform: uppercase;
}
ul li.nav-last a:hover{
  border-bottom: 0.1em white solid;
}
li {
  margin-bottom: 20px;
}
li:hover {
  cursor: pointer;
}
a {
  text-decoration: none;
}
ul li.nav-first a{
  color: #fff;
}
ul li.nav-last a{
  color: rgb(190, 184, 184);
}
.close{
  position:absolute;
  left: calc(100% + 15px);
  top: 30px;
  text-transform: uppercase;
  font-weight: bold;
}
.close:hover {
  border-bottom: .1em white solid;
}
.div-close {
  transform: translateX(-250px);
}
</style>
