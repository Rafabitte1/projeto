<script setup>
import { ref, reactive } from 'vue'

const titulo = ref('Meu Vuejs')
const mostrarResultado = ref(false)
const categoria = [
{
  id:1,
  nome: 'Joia'
},
{
  id:2,
  nome: 'Eletrônico'
},
{
  id:3,
  nome: 'Móveis'
},
{
  id:4,
  nome: 'Comestico'
},

{
  id:5,
  nome: 'Decoração'
}

]



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
      <hr>
      
      <label for="Nome:"></label>
      <input type="text" v-model="produto.nome" required>
      <div class="row">
      <label for="">Preco:</label>
      <input type="number" v-model="produto.preco">
    </div>
      <div class="row">
        <label for="">Quantidade</label>
        <input type="number" v-model="produto.quantidade">

      </div>
      <fieldset>
      <legend>Categoria</legend>


    <div class="row" v-for="categoria in categoria" :key="categoria.id">
     <input type="checkbox" v-model="produto.categoria.id" :value="categoria.id" /> {{ categoria.nome }}
    </div>

  </fieldset>
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
.formulario.row{
width: 80%;

}
.resultado {
  background-color: rgb(245, 231, 220);
  display: flex;
}
.formulario .enviar {
  position: relative;
}
</style>
