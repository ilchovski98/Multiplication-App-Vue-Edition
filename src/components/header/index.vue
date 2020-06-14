<template>
  <div>
      <slot></slot>
  </div>
</template>

<script>
export default {
    name: 'header',
    props: [],
    data() {
        return {
            title: ''
        }
    }
}
</script>

<style>

</style>