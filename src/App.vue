<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png"><span class="img-text">andelay</span>
    <HelloWorld msg="Industries"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.img-text {
  position: absolute;
  top:220px;
  left: 710px;
  font-size: 25px;
}
</style>
