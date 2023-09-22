<script setup>
import { reactive } from 'vue';

const state = reactive({
  filtro: 'soma',
  num1: '',
  num2: '',
  resultado: '',
})

const sum = () => {
  const resultadoSoma = state.num1 + state.num2
  state.resultado = resultadoSoma;
  return state.resultado
}

const sub = () => {
  const resultadoSubtracao = state.num1 - state.num2
  state.resultado = resultadoSubtracao;
  return state.resultado
}

const mult = () => {
  const resultadoMultiplicacao = state.num1 * state.num2
  state.resultado = resultadoMultiplicacao;
  return state.resultado
}

const div = () => {
  const resultadoDivisao = state.num1 / state.num2
  state.resultado = resultadoDivisao
  return state.resultado
}
</script>

<template>
  <h1>ola</h1>
</template>

<style scoped>

</style>
