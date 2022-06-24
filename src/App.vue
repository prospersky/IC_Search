<template>
  <div id="app">
    <MainHeader/>
        <!-- <img :src='image'/> -->
        <!-- <img src="./assets/logo.jpg" alt=""> -->
    <SelectImage/>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import SelectImage from './components/SelectImage.vue'

export default {
  components: {
    'SelectImage': SelectImage,
    'MainHeader': MainHeader
  }
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
