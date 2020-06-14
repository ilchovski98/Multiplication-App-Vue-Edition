<template>
  <div>
    <div v-for="index in count" :key="index">
        <multiplication-template :addComponent="addComponent" :count="count" class="space"></multiplication-template>
    </div>
  </div>
</template>

<script>
import MultiplicationTemplate from '../multiplicationTemplate'

export default {
    name: 'InfiniteGame',
    components: {
        MultiplicationTemplate
    },
    props: ['count', 'addComponent']
    
}
</script>

<style>

</style>