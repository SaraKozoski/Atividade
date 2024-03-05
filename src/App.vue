<script setup>
import { ref } from "vue";
const nome = 'Sara'
const idade = 15
const contador = ref(0);

function inverter(texto) {
  return texto.split('').reverse().join('').toUpperCase();
}

function saudacao() {
  return `Olá, ${nome}!`
}

function incrementar() {
  contador.value++;
}

function decrementar() {
  if (contador.value > 0) {
    contador.value--;
  }
}

function reiniciar() {
    contador.value = 0;
  }
</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }} </p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é: {{ inverter(nome) }} </p>
    <hr />
    <p> Exemplo de saudação usando função</p>
    <p> {{ saudacao() }} </p>
    <hr>
    <div>
      <h1>Contador</h1>
      <p> {{ contador }} </p>
      <button @click="incrementar">Incrementar</button>
      <button @click="decrementar">Decrementar</button>
      <button @click="reiniciar">Reiniciar</button>
      <div :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }">
      <p v-if="contador >10" >Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.info {
  background-color: rgb(0, 0, 0);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
} 

button{
  background-color: rgb(0, 0, 0);
  color: aliceblue;
}
</style>
