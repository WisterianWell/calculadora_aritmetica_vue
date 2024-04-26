<script setup>
import { reactive } from 'vue';
import Calculadora from './components/Calculadora.vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  operacao: 'adicao',
})

const calculaOperacoes = () => {
  const { numero1, numero2, operacao } = estado;

  switch (operacao) {
    case 'adicao':
      return parseInt(numero1) + parseInt(numero2);
    case 'subtracao':
      return parseInt(numero1) - parseInt(numero2);
    case 'multiplicacao':
      return parseInt(numero1) * parseInt(numero2);
    case 'divisao':
      return parseInt(numero1) / parseInt(numero2);
  }
}
</script>

<template>
  <div class="container p-5">
    <Calculadora :get-numero1="evento => estado.numero1 = evento.target.value" :get-numero2="evento => estado.numero2 = evento.target.value" :trocarOperacao="evento => estado.operacao = evento.target.value" :calculaOperacoes=" calculaOperacoes()"/>
  </div>
</template>

<style scoped>
</style>
