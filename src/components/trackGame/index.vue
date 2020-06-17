<template>
  <div>
    <div v-for="index in count" :key="index">
      <timer #default="{stop, formattedTime }">
        <multiplication-template :component="component" :limitOfTen="limitOfTen" :index="index" :stopTimerExistance="true" :start="start" :stop="stop" :addComponent="addComponent" :count="count" class="space">
        <template  #timer>
          <p class="timer">{{ formattedTime }}</p>
        </template>
      </multiplication-template>
      </timer>
    </div>
    <div id="finish" v-if="reachTenExercises == true">
      <h1>Congradulations! You Finished!</h1>
    </div>
  </div>
</template>

<script>
import MultiplicationTemplate from '../multiplicationTemplate'
import Timer from '../timer'

export default {
    name: 'TrackGame',
    components: {
      MultiplicationTemplate,
      Timer
    },
    props: ['count', 'addComponent', 'component'],
    data() {
      return {
        reachTenExercises: false
      }
    },
    methods: {
      limitOfTen() {
        if (this.count < 10) {
          this.addComponent();
        } else if (this.count == 10 && this.reachTenExercises == false) {
          this.reachTenExercises = true;
        }
      }
    }
}
</script>

<style>
.timer {
  margin-right: 35px;
}
</style>