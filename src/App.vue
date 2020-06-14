<template>
  <div id="app">

    <div class="navigator">
      <button class="btn btn-primary" @click="component='InfiniteGame'; count=1">Infinity</button>
      <button class="btn btn-primary" @click="component='TrackGame'; count=1">For Time</button>
      <button class="btn btn-primary">Double Digits</button>
    </div>

    <component v-bind:is="component" :count="count" :addComponent="addComponent"></component>

  </div>
</template>

<script>
import InfiniteGame from './components/infiniteGame/index.vue'
import TrackGame from './components/trackGame/index.vue'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    InfiniteGame,
    TrackGame
  },
  data() {
    return {
      count: 1,
      component: 'InfiniteGame'
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

.navigator {
  background-color: grey;
  height: 70px;
  width: 100%;
  display: flex;
  align-content: center;
  justify-content: space-around;
  align-items: center;
}
</style>
