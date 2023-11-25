<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  num1: '0',
  num2: '0',
  resultado: 'adicao'
})

const filtraconta = () => {
  const { resultado, num1, num2 } = estado;

  switch (resultado) {
    case 'subtracao':
      return realizarOperacao(num1, num2, (a, b) => a - b);
    case 'multiplicacao':
      return realizarOperacao(num1, num2, (a, b) => a * b);
    case 'divisao':
      return realizarOperacao(num1, num2, (a, b) => a / b);
    default:
      return realizarOperacao(num1, num2, (a, b) => a + b);
  }
}

const realizarOperacao = (num1, num2, operacao) => {
  return operacao(parseFloat(num1), parseFloat(num2));
}
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario 
      :filtraQualOperacao="estado.resultado"
      :pegaNum1="evento => estado.num1 = evento.target.value"
      :pegaNum2="evento => estado.num2 = evento.target.value" 
      :trocarOperacao="evento => estado.resultado = evento.target.value"></Formulario> 
    <Resultado :filtraOperacao="filtraconta()"/>
  </div>
</template>

<style scoped>
.container {
  width: 640px;
  background-color: darkgray;
  border-radius: 10px;
  padding: 24px;
  margin-top: 10vh;
}
</style>