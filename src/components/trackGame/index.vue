<template>
  <div>
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
import MultiplicationTemplate from '../multiplicationTemplate'
import Timer from '../timer'

export default {
    name: 'TrackGame',
    components: {
      MultiplicationTemplate,
      Timer
    },
    props: ['count', 'addComponent']
}
</script>

<style>

</style>