<template>
  <div class="container">
    <h1>Editar Perfil</h1>
    <form @submit.prevent="submitForm" class="form">
      <div class="form-group">
        <label for="nome">Nome:</label>
        <input type="text" id="nome" v-model="user.nome" required />
      </div>
      <div class="form-group">
        <label for="email">E-mail:</label>
        <input type="email" id="email" v-model="user.email" required />
      </div>
      <div class="form-group">
        <label for="senha">Senha:</label>
        <input type="password" id="senha" v-model="user.senha" required />
      </div>
      <div class="form-group">
        <label for="confirmar-senha">Confirmar Senha:</label>
        <input
          type="password"
          id="confirmar-senha"
          v-model="confirmarSenha"
          required
        />
      </div>
      <div class="form-group">
        <label for="data-nascimento">Data de Nascimento:</label>
        <input type="date" id="data-nascimento" v-model="user.dataNascimento" required />
      </div>
      <div class="form-group">
        <label for="endereco">Endereço:</label>
        <input type="text" id="endereco" v-model="user.endereco" required />
      </div>
      <div class="form-group">
        <label for="cidade">Cidade:</label>
        <input type="text" id="cidade" v-model="user.cidade" required />
      </div>
      <div class="form-group">
        <label for="estado">Estado:</label>
        <select id="estado" v-model="user.estado" required>
          <option value="AC">Acre</option>
          <option value="AL">Alagoas</option>
          <option value="AP">Amapá</option>
          <option value="AM">Amazonas</option>
          <option value="BA">Bahia</option>
          <option value="CE">Ceara</option>
          <option value="DF">Distrito Federal</option>
          <option value="ES">Espirito Santo</option>
          <option value="GO">Goias</option>
          <option value="MA">Maranhão</option>
          <option value="MT">Mato Gross</option>
          <option value="MS">Mato Grosso do Sul</option>
          <option value="PA">Pará</option>
          <option value="PB">Paraíba</option>
          <option value="PR">Paraná</option>
          <option value="PE">Pernabuco</option>
          <option value="PI">Piaui</option>
          <option value="RJ">Rio de Jaineiro</option>
          <option value="RN">Rio Garnde do Norte</option>
          <option value="RS">Rio grande do Sul</option>
          <option value="RR">Roraima</option>
          <option value="SC">Snata Catarina</option>
          <option value="SP">São Paulo</option>
          <option value="SE">Sergipe</option>
          <option value="TO">Toncantins</option>
        </select>
      </div>
      <div class="form-group">
        <label for="hobbies">Hobbies:</label>
        <input type="text" id="hobbies" v-model="user.hobbies" required />
      </div>
      <div class="form-group">
        <label for="linguagens">Linguagens de Programação:</label>
        <input type="text" id="linguagens" v-model="user.linguagens" required />
      </div>
      <div class="form-group">
        <label for="biografia">Biografia:</label>
        <textarea id="biografia" v-model="user.biografia" required></textarea>
      </div>
      <button type="submit" class="button">Salvar</button>
    </form>
    <div v-if="showResult" class="result">
      <h2>Perfil Editado:</h2>
      <p><strong>Nome:</strong> {{ user.nome }}</p>
      <p><strong>E-mail:</strong> {{ user.email }}</p>
      <p><strong>Senha:</strong> *********</p>
      <p><strong>Data de Nascimento:</strong> {{ user.dataNascimento }}</p>
      <p><strong>Endereço:</strong> {{ user.endereco }}</p>
      <p><strong>Cidade:</strong> {{ user.cidade }}</p>
      <p><strong>Estado:</strong> {{ user.estado }}</p>
      <p><strong>Hobbies:</strong> {{ user.hobbies }}</p>
      <p><strong>Linguagens de Programação:</strong> {{ user.linguagens }}</p>
      <p><strong>Biografia:</strong> {{ user.biografia }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const user = {
  nome: ref(''),
  email: ref(''),
  senha: ref(''),
  confirmarSenha: ref(''),
  dataNascimento: ref(''),
  endereco: ref(''),
  cidade: ref(''),
  estado: ref(''),
  hobbies: ref(''),
  linguagens: ref(''),
  biografia: ref(''),
};

let confirmarSenha = ref('');
let showResult = ref(false);

const submitForm = () => {
  showResult.value = true;
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: 50px auto;
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  margin-bottom: 30px;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  color: #666; /* Cor do texto do label */
}

input[type="text"],
input[type="email"],
input[type="password"],
select {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

button {
  padding: 10px 20px;
  background-color: #9BBAE8; /* Cor de fundo do botão */
  color: #fff; /* Cor do texto do botão */
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s; /* Transição suave na mudança de cor de fundo */
}

button:hover {
  background-color: #7a93c9; /* Cor de fundo do botão ao passar o mouse */
}

.result {
  margin-top: 20px;
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
}
</style>
