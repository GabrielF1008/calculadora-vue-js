<script setup>
import { reactive } from 'vue';


const estado = reactive({
  numero1: parseInt(0),
  numero2: parseInt(0)
})

function exibeResultadoMultiplicacao() {
  return parseInt(estado.numero1) + parseInt(estado.numero2)
}
</script>

<template>
  <div>
    <select>
      <option value="subtracao">Subtração</option>
      <option value="adicao">Adição</option>
      <option value="divisao">Divisão</option>
      <option value="multiplicacao">Multiplicação</option> 
    </select>
  </div>
  <form>
    <br>
    <input @keyup="evento => estado.numero1 = evento.target.value" type="number" placeholder="Número 1"> <br>
    <input @keyup="evento => estado.numero2 = evento.target.value" type="number" placeholder="Número 2"> <br>
    <span> Resultado: {{ exibeResultadoMultiplicacao() }} </span>
  </form>
</template>

<style scoped></style>
