<script setup lang="ts">
import { reactive } from 'vue'
import numero from './components/numero.vue'
import operador from './components/operador.vue'
import resultado from './components/resultado.vue'

const state = reactive({
  number1: '',
  number2: '',
  operator: '+',
  result: '0'
})

const setOperator = () => {
  switch (state.operator) {
    case '+':
      return (state.result = (Math.floor(state.number1 * 100 + state.number2 * 100) / 100).toFixed(
        2
      ))
    case '-':
      return (state.result = (Math.floor(state.number1 * 100 - state.number2 * 100) / 100).toFixed(
        2
      ))
    case '/':
      return (state.result = (state.number1 / state.number2).toFixed(2))
    case '*':
      return (state.result = (state.number1 * state.number2).toFixed(2))
  }
}

const setNuber1 = (ev) => {
  state.number1 = parseFloat(ev.target.value)
  if (state.number1 && state.number2 != Number) {
    setOperator()
  } else state.result = '?'
}

const setNuber2 = (ev) => {
  state.number2 = parseFloat(ev.target.value)
  if (state.number1 && state.number2 != Number) {
    setOperator()
  } else state.result = '?'
}

const setcu = (ev) => {
  state.operator = ev.target.value
  if (state.number1 && state.number2 != Number) {
    setOperator()
  }
}
</script>

<template>
  <div class="container">
    <h1 class="title">Calculadora</h1>
    <resultado class="resultado" :result="state.result" />
    <form>
      <numero :change="setNuber1" />
      <operador :option="setcu" />
      <numero :change="setNuber2" />
    </form>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva;
}

body {
  background-color: #393a3c;
}

.container {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.resultado {
  margin-top: 24px;
}

form {
  width: 50%;
  max-width: 484px;
  margin-top: 24px;
  display: grid;
  grid-template-columns: 40% 10% 40%;
  gap: 5%;
}

.title {
  margin-top: 30px;
  color: rgb(248, 251, 228);
}
</style>
