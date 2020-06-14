<template>
  <div class="navigator">
    <button class="btn btn-primary">For Time</button>
    <button class="btn btn-primary">Infinite</button>
    <button class="btn btn-primary">Double Digits</button>
  </div>
</template>

<script>
export default {
    name: "Navigation",
    
}
</script>

<style>
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