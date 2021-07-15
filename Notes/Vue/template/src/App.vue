<template>
  <div id="app">
    <Calculator></Calculator>
  </div>
</template>

<script>

import Calculator from './components/calc'

export default {
  name: 'App',


  components: {
    Calculator
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
