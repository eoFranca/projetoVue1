<script setup>
import { ref, computed } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const confsenha = ref('')
const dataNasc = ref('')
const endereco = ref('')
const estado = ref('')
const cidade = ref('')
const hobbies = ref('')
const lingProg = ref('')
const biografia = ref('')

const mostrar = ref(false)

const Errsenha = ref(false)

function login() {
  if (nome.value.length > 3 && senha.value == confsenha.value) {
    mostrar.value = true
  }
  else if (senha.value !== confsenha.value) {
    Errsenha.value = true

  }
}

function fecharErr() {
  Errsenha.value = false
}

function fecharInfo() {
  mostrar.value = false
}
</script>

<template>
  <div class="form">
    <h1>Formulario</h1>
    <label for="nome">Nome</label> <br>
    <input type="text" v-model="nome" required><br>


    <label for="email">email</label><br>
    <input type="email" name="a" id="email" v-model="email" required><br>
    <label for="password">senha</label><br>
    <input type="password" v-model="senha" required><br>
    <label for="password">confirmar senha</label><br>
    <input type="password" v-model="confsenha" required><br>
    <label for="">Data de Nascimento</label><br>
    <input type="date" v-model="dataNasc" required><br>

    <label for="Endereço">Endereço</label><br>
    <input type="text" v-model="endereco" required>
    <br>
    <label for="">Estado</label>
    <br>
    <select v-model="estado">
      <option value="">Selecione seu Estado</option>
      <option value="AC">AC</option>
      <option value="AL">AL</option>
      <option value="AM">AM</option>
      <option value="ES">ES</option>
      <option value="GO">GO</option>
      <option value="MA">MA</option>
      <option value="MT">MT</option>
      <option value="MS">MS</option>
      <option value="MG">MG</option>
      <option value="PA">PA</option>
      <option value="PB">PB</option>
      <option value="PR">PR</option>
      <option value="PE">PE</option>
      <option value="PI">PI</option>
      <option value="RJ">RJ</option>
      <option value="RN">RN</option>
      <option value="RO">RO</option>
      <option value="RS">RS</option>
      <option value="RR">RO</option>
      <option value="SC">SC</option>
      <option value="SE">SE</option>
      <option value="SP">SP</option>
      <option value="TO">TO</option>
    </select><br>
    <label for="">Cidade</label><br>
    <input type="text" v-model="cidade"><br>
    <label for="">Hobbies</label><br>
    <input type="text" v-model="hobbies"><br>
    <label for="">Linguagens de programação</label><br>
    <input type="text" v-model="lingProg" required> <br>
    <label for="">Biografia</label><br>
    <textarea v-model="biografia" required></textarea>


    <button type="submit" @click="login">Cadastrar-se</button>
  </div>


  <div v-if="mostrar" class="mensagem">
    <h1>Mostrar</h1>
    <p>nome: {{ nome }}</p>
    <p>email: {{ email }}</p>
    <p>data nascimento: {{ dataNasc }}</p>
    <p>senha: {{ senha }}</p>
    <p>confirmaçao da senha: {{ confsenha }}</p>
    <p>endereco: {{ endereco }}</p>
    <p>estado: {{ estado }}</p>
    <p>cidade: {{ cidade }}</p>
    <p>hobbies: {{ hobbies }}</p>
    <p>Linguagens de programação: {{ lingProg }}</p>
    <h4>Biografia:</h4>
    <textarea>{{ biografia }}</textarea>

    <button class="btInfo" @click="fecharInfo">Fechar</button>
  </div>
  <div v-if="Errsenha">
    <div class="err">
      <h3>As senhas não estão iguais :/ </h3>
    </div>
    <button class="botaoerr" @click="fecharErr">Ok</button>
  </div>
</template>

<style scoped>
.form {
  height: 650px;
  width: 200px;
  padding: 5%;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  border: 2px solid rgb(228, 228, 228);
  border-radius: 20px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.mensagem {
  height: 650px;
  width: 200px;
  padding: 5%;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  border: 2px solid rgb(228, 228, 228);
  border-radius: 20px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  margin-left: 5%;
}

button {
  padding: 12%;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  border: 2px solid rgb(228, 228, 228);
  border-radius: 20px;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  font-size: large;
  margin-left: 15px;
}

.err {
  height: 100px;
  padding: 8%;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  border: 2px solid rgb(228, 228, 228);
  border-radius: 20px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  margin-left: 5%;
}

.botaoerr {
  padding: 5%;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  border: 2px solid rgb(228, 228, 228);
  border-radius: 50%;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  font-size: large;
  margin-top: 3px;
}

.btInfo {
  padding: 5%;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  border: 0px solid;
  color: aliceblue;
  background-color: rgb(83, 117, 126);
  font-size: large;
  margin-top: 3px;
}
</style>
