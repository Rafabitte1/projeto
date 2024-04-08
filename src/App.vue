<template>
  <div id="app">
    <h1>Editar Perfil</h1>
    <form @submit.prevent="submitForm">
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
          <!-- Add other states here -->
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
      <button type="submit">Salvar</button>
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

<script >
export default {
  data() {
    return {
      user: {
        nome: '',
        email: '',
        senha: '',
        confirmarSenha: '',
        dataNascimento: '',
        endereco: '',
        cidade: '',
        estado: '',
        hobbies: '',
        linguagens: '',
        biografia: '',
      },
      confirmarSenha: '',
      showResult: false,
    };
  },
  methods: {
    submitForm() {
      // Handle form submission here
      this.showResult = true;
    },
  },
};
</script>

<style sco>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.form-group {
  margin-bottom: 1rem;
}

.result {
  margin-top: 2rem;
  border: 1px solid #ccc;
  padding: 1rem;
  background-color: #f5f5f5;
}

.template{
  min-height: 100vh;
  background-color: #81259d;
  font-family: sans-serif;
  display: grid;
  place-items: center;
}

.p{
  font-size: 1.3125rem;
  font-weight: 700;
  color: #222;
  margin-bottom: 5rem;
}

.form{
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 28rem;
  background: #fff;
  padding: 4rem;
  border-radius: 0.5rem;
  box-shadow: 0 0 1.8rem rgba(0, 0, 0, 0.15);
}
.label{
  width: 100%;
  color: #777;
  align-self: flex-start;
  transition: 0.15s linear;
}
label:focus-within{
  color: #8d3dc8;
}
.inpunt{
  font-size: 1.1875rem;
  color: #404040;
  padding: 1rem 0 0.5rem 0;
  width: 100%;
  border: none;
  border-color: #a0a0a0;
  border-bottom-width: 1px;
  border-bottom-style: dotted;
  margin-bottom: 3rem;
  transition: 0.15s linear;
}
.button {
font-size: 0.8125rem;
line-height: 2rem;
font-weight: 700;
text-transform: uppercase;
width: 100%;
padding: 1rem 2rem;
cursor: pointer;
background: transparent;
color: purple;
border: 1px solid currentColor; 
border-radius: 4px;
margin-top: 0.5rem;

}
</style>

