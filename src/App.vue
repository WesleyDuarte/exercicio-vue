<script setup>
import { reactive } from 'vue';
import Cabecalho from './assets/components/Cabecalho.vue';
import Formulario from './assets/components/Formulario.vue';
import Resultado from './assets/components/Resultado.vue';

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
  <div class="container">
    <div class="background-calculator">
      <Cabecalho />
      <Formulario :valorPrimeiroInput="event => state.num1 = Number(event.target.value)" :valorSegundoInput="event => state.num2 = Number(event.target.value)" :filtro="state.filtro" :selecionaFiltro="event => state.filtro = event.target.value"/>
      <Resultado :filtro="state.filtro" :funcaoSoma="sum()" :funcaoSub="sub()" :funcaoMult="mult()" :funcaoDivisao="div()" />
    </div>
  </div>
</template>

<style scoped>

</style>
