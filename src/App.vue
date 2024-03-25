<script setup>
import { ref, reactive } from 'vue'

const titulo = ref('Meu Vuejs')
const mostrarResultado = ref(false)

const produto = reactive({
  nome: '',
  preco: 0,
  estoque: 0,
  categoria: []
})

function formatarpreco(preco) {
  return `R$ ${preco.toFixed(2).replace('.', ',')}`
}
</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div class="formulario">
      <h2>formulario</h2>
      <input type="text" v-model="titulo.value">
      <hr>
      <label for="Nome:"></label>
      <input type="text" v-model="produto.nome">
      <label for="">Preco:</label>
      <input type="number" v-model="produto.preco">
      <div>
        <button @click="mostrarResultado = !mostrarResultado" class="enviar">enviar</button>
      </div>
      <form class="form">
      </form>
      <div v-if="mostrarResultado" class="resultado">
        <h2>resultado</h2>
        <h3>Dados do produtos</h3>
        <p>Nome: {{ produto.nome }}</p>
        <p>Preço: {{ formatarpreco(produto.preco) }}</p>
        <p>Estoque: {{ produto.estoque }}</p>
        <p>Categoria: {{ produto.categoria }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  column-gap: 2rem;
  margin-top: 1rem;
}
.formulario,
.resultado {
  min-height: 80vh;
  width: 48vw;
  padding: 10px;
  border-radius: 10px;
  
}
.formulario {
  background-color: azure;
}
.resultado {
  background-color: rgb(245, 231, 220);
  display: flex;
}
.formulario .enviar {
  position: relative;
}
</style>
