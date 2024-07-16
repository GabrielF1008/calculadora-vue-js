<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Operacao from './components/Operacao.vue';
import Resultado from './components/Resultado.vue';


const estado = reactive({
  num1: '',
  num2: '',
  operacao: '+'
})

const resultado = () => {
  const {operacao} = estado
  switch(operacao) {
    case '-':
      return parseFloat(estado.num1) - parseFloat(estado.num2)
    case '*':
      return parseFloat(estado.num1) * parseFloat(estado.num2)
    case '/':
      return parseFloat(estado.num1) / parseFloat(estado.num2)
    default:
      return parseFloat(estado.num1) + parseFloat(estado.num2)
  }
}
</script>

<template>
    <body>
      <div class="container">
        <Cabecalho />
        <Operacao 
          :operacao="evento => estado.operacao = evento.target.value" 
          :num1="evento => estado.num1 = evento.target.value" 
          :num2="evento => estado.num2 = evento.target.value" />
        <Resultado 
          :num1="estado.num1"
          :num2="estado.num2"
          :resultado="resultado()"
        />
      </div>
    </body>
</template>

<style scoped></style>
