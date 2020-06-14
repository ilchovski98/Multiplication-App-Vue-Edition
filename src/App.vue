<template>
  <div id="app">
    <navigation></navigation>
    <div v-for="index in count" :key="index">
      <timer #default="{stop, formattedTime }">
        <multiplication-template :start="start" :stop="stop" :addComponent="addComponent" :count="count" class="space">
        <template #timer>
          {{ formattedTime }}
        </template>
      </multiplication-template>
      </timer>
    </div>
  </div>
</template>

<script>
import MultiplicationTemplate from './components/multiplicationTemplate'
import Navigation from './components/navigation'
import Timer from './components/timer'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    MultiplicationTemplate,
    Navigation,
    Timer
  },
  data() {
    return {
      count: 1
    }
  },
  methods: {
    addComponent() {
      this.count += 1;
    }
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

.space {
  margin-top: 20px;
}
</style>
