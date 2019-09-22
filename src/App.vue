<template>
  <div id="app">
    <img alt="logo" src="./assets/logo2.png" width=200>
    <KittenWeights/>
  </div>
</template>

<script>
import KittenWeights from './components/KittenWeights.vue'
import Chartkick from 'vue-chartkick'
import Chart from 'chart.js'
import Vue from 'vue'

Vue.use(Chartkick.use(Chart))

export default {
  name: 'app',
  components: {
    KittenWeights
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
</style>
