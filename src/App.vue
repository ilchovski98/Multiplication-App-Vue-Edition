<template>
  <div id="app">
    <header>
      <template>
        <h1>{{ title }}</h1>
      </template>
    </header>
    <div class="navigator">
      <button class="btn btn-primary" @click="component='InfiniteGame'; count=1; title='Infinity Mode'">Infinity</button>
      <button class="btn btn-primary" @click="component='TrackGame'; count=1; title='Time Mode' ">For Time</button>
      <button class="btn btn-primary">Double Digits</button>
    </div>

    <component v-bind:is="component" :count="count" :addComponent="addComponent"></component>

  </div>
</template>

<script>
import InfiniteGame from './components/infiniteGame/index.vue'
import TrackGame from './components/trackGame/index.vue'
import Header from './components/header/index.vue'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    InfiniteGame,
    TrackGame,
    Header
  },
  data() {
    return {
      count: 1,
      component: 'InfiniteGame',
      title: 'Infinity Mode'
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
