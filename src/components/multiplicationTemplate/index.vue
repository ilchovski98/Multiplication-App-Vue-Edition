<template>
  <div id="main" :class="{green: correct, red: !correct}">
      <div id="content">
          <slot name="timer"></slot>
          <p>{{ number1 }} X {{ number2 }} =</p>
          <input @keyup.enter="check" ref='inputField' type="number" v-model="enteredNumber">
          <button id="btns" class="btn btn-primary" @click="check">Submit</button>
      </div>
  </div>
</template>

<script>
export default {
    name: "MultiplicationTemplate",
    props: ['count', 'addComponent', 'start', 'stop', 'stopTimerExistance', 'index'],
    data() {
        return {
            number1: Math.floor(Math.random() * 10),
            number2: Math.floor(Math.random() * 10),
            enteredNumber: 0,
            result: undefined,
            correct: false,
            
        }
    },
    methods: {
        randomFunction() {
            const num1Random = Math.floor(Math.random()*10);
            this.number1 = num1Random;
            const num2Random = Math.floor(Math.random()*10);
            this.number2 = num2Random;
            console.log(this.number1, this.number2);
            
        },
        check() {
            const calcResult = this.number1 * this.number2;
            if (this.enteredNumber == calcResult) {
                this.correct = true;
                if (this.stopTimerExistance == true) {
                    this.stop();
                }
                this.addComponent();
            } else {
                this.correct = false;
            }
            console.log(this.enteredNumber);
            console.log(this.correct);
            
        },
        focused() {
            this.$refs.inputField.focus();
        }
    },
    computed: {
        colorful() {
            return {
                backgroundColor: this
            }
        }
    },
    mounted() {
        this.focused();
    }
}
</script>

<style>

#main {
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
    margin-left: 30px;
}

.red {
    background-color: red;
}

.green {
    background-color: greenyellow;
}

.content {
  background-image: url("../../assets/backgrounds/09.jpg");
  background-size: cover;
  height: 1000px;
  opacity: 0.5;
}
</style>