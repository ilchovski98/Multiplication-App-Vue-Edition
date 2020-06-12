<template>
  <div>
      <div>
          <p>{{ number1 }} X {{ number2 }} =</p>
          <input type="number">
          <button @click="randomFunction">Click</button>
      </div>
  </div>
</template>

<script>
export default {
    name: "MultiplicationTemplate",
    props: [],
    data() {
        return {
            number1: 0,
            number2: 0
        }
    },
    methods: {
        randomFunction() {
            const num1Random = Math.floor(Math.random()*10);
            this.number1 = num1Random;
            const num2Random = Math.floor(Math.random()*10);
            this.number2 = num2Random;
            console.log(this.number1, this.number2);
            
        }
    }
}
</script>

<style>

</style>