<script setup>
import { reactive } from 'vue';


const estado = reactive({
  numero1: 0,
  numero2: 0,
  resultado: 0
})

function alteraNumero1(evento) {
  evento => estado.numero1 = evento.target.value
  console.log(evento.target.value)
}

function alteraNumero2(evento) {
  evento => estado.numero2 = evento.target.value
  console.log(evento.target.value)
  estado.resultado = estado.numero1 + estado.numero2
}
</script>

<template>
  <form action="">
    <input type="number" name="numero1" id="numero1" @keyup="alteraNumero1"> <br><br>
    <input type="number" name="numero2" id="numero2" @keyup="alteraNumero2"> <br><br>
    <input type="number" name="resultado" id="resultado">
    {{ estado.resultado }}
    <select>
      <option value="adicao">Adição</option>
      <option value="subtracao">Subtração</option>
      <option value="divisao">Divisão</option>
      <option value="multiplicacao">Multiplicação</option>
    </select>
  </form> <br>
</template>

<style scoped></style>
