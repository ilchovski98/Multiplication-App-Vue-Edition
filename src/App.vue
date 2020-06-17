<template>
  <div id="app">
    <header :class="headerClass">
      <h1 class="title">{{ title }}</h1>
    </header>

    <div class="navigator">
      <button class="btn" @click="component='InfiniteGame'; infinityTheme()">Infinity</button>
      <button class="btn" @click="component='TrackGame'; trackTheme()">For Time</button>
      <button class="btn">Double Digits</button>
    </div>
    
    <div :class="bodyClass">
      <component  v-bind:is="component" :component="component" :count="count" :addComponent="addComponent"></component>
    </div>

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
      title: 'Infinity Mode',
      headerClass: 'headerInfinity',
      bodyClass: 'backgroundsInfinity'
    }
  },
  methods: {
    addComponent() {
      this.count += 1;
    },
    infinityTheme() {
      this.headerClass = 'headerInfinity';
      this.bodyClass = 'backgroundsInfinity';
      this.title = 'Infinity Mode';
      this.count = 1;

    },
    trackTheme() {
      this.headerClass = 'headerTrack';
      this.bodyClass = 'backgroundsTrack';
      this.title = 'Time Mode';
      this.count = 1;
    }
  },
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}

.space {
  margin-top: 20px;
}

.navigator {
  background-color: #ffffff;
  height: 70px;
  width: 100%;
  display: flex;
  align-content: center;
  justify-content: space-around;
  align-items: center;
  
}

.headerInfinity {
  display: flex;
  justify-content: center;
  height: 22vh;
  background-image: url("./assets/backgrounds/09.jpg");
  background-size: cover;
}

.headerTrack {
  display: flex;
  justify-content: center;
  height: 22vh;
  background-image: url("./assets/backgrounds/10.jpg");
  background-size: cover;
}

.title {
  color: #fff;
  align-self: center;
  text-shadow: 0 0 2px black;
}

.backgroundsInfinity {
  background-image: url("./assets/backgrounds/09-opacity.jpg");
  /* background-size: cover;
  height: 300vh;
  width: 100%; */
  box-shadow: 0px 6px 8px 3px rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  background-repeat:no-repeat;
  background-attachment:fixed;
  height: 100vh;
  
}

.backgroundsTrack {
  background-image: url("./assets/backgrounds/10-opacity.jpg");
  background-size: cover;
  height: 100vh;
  box-shadow: 0px 6px 8px 3px rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
</style>
