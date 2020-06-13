<template>
  <div id="main">
      <div id="content">
          <p>{{ number1 }} X {{ number2 }} =</p>
          <input type="number">
          <button id="btns" class="btn btn-primary" @click="randomFunction">Click</button>
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

#main {
    background-color: grey;
    width: 600px;
    height: 110px;
    margin-left: auto;
    margin-right: auto;
    display:inline-block;
    border-radius: 15px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

}

#content {
    margin-top: 35px;
    font-size: 25px;
}

p {
    display:inline-block;
    padding: 0px;
    margin: 0px;
    margin-right: 10px;
}

input {
    display:inline-block;
    height: 28px;
    font-size: 25px;
    width: 100px; 
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

#btns {
    margin-left: 10px;
}
</style>