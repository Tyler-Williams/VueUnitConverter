<template>
  <div id="app">
    <h1>Universal Unit Converter</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <converter/>
  </div>
</template>

<script>
import Converter from '@/components/Converter.vue'

export default {
  name: 'app',
  components: {
    Converter
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
h1 {
  font-size: 300%;
}
</style>
