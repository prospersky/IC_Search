<template>
  <div id="app">
    <MainHeader> </MainHeader>
    <img src="./assets/logo.png">
    <img src="./assets/logo.jpg">
    <PictureInput></PictureInput>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import PictureInput from './components/PictureInput.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    'PictureInput' : PictureInput,
    'MainHeader' : MainHeader
  }
}
</script>

<style>
body {
  text-align: center;
  background-color: #f6f6f8
}
input {
  border-style: grove;
  width: 200px;
}
button {
  border-style: groove;
}
.shawdow{
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
}

img {
  width: 300px;
  height: 150px;
  object-fit: contain;
}

</style>
