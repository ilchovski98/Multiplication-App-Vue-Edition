<template>
  <div id="app">
    <multiplication-template></multiplication-template>
  </div>
</template>

<script>
import MultiplicationTemplate from './components/multiplicationTemplate'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    MultiplicationTemplate
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
