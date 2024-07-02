<script setup>
import { ref } from 'vue'

const dados = ref({
  nome: '',
  sobrenome: '',
  senha: '',
  confirmSenha: '',
  dataNasc: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: [],
  linguagens: '',
  bio: ''
})

let estados = [
  { name: 'AC' },
  { name: 'AL' },
  { name: 'AP' },
  { name: 'AM' },
  { name: 'BA' },
  { name: 'CE' },
  { name: 'DF' },
  { name: 'ES' },
  { name: 'GO' },
  { name: 'MA' },
  { name: 'MT' },
  { name: 'MS' },
  { name: 'MG' },
  { name: 'PA' },
  { name: 'PB' },
  { name: 'PR' },
  { name: 'PE' },
  { name: 'PI' },
  { name: 'RJ' },
  { name: 'RN' },
  { name: 'RS' },
  { name: 'RO' },
  { name: 'RR' },
  { name: 'SC' },
  { name: 'SP' },
  { name: 'SE' },
  { name: 'TO' }
]

const enviar = ref(true);
</script>

<template>
  <main>
    <form v-if="enviar">
      <h1>Crie seu perfil</h1>
      <div class="row mb-4">
        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input type="text" class="form-control" v-model="dados.nome" placeholder="Nome" />
          </div>
        </div>

        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input type="text" class="form-control" v-model="dados.sobrenome" placeholder="Sobrenome" />
          </div>
        </div>
      </div>

      <!-- EMAIL -->
      <div data-mdb-input-init class="form-outline mb-4">
        <input type="email" class="form-control" v-model="dados.email" placeholder="E-mail" />
      </div>

      <!-- SENHA -->
      <div data-mdb-input-init class="form-outline mb-4">
        <input type="password" class="form-control" v-model="dados.senha" placeholder="Senha" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="password" class="form-control" v-model="dados.confirmSenha" placeholder="Confirme sua senha" />
      </div>

      <!-- DATA DE NASCIMENTO -->
      <div data-mdb-input-init class="form-outline mb-4">
        <label for="dataNasc">Data de nascimento:</label>
        <input type="date" id="dataNasc" class="form-control" v-model="dados.dataNasc" placeholder="Data de nascimento" />
      </div>

      <!-- ENDEREÇO -->
      <div data-mdb-input-init class="form-outline mb-4">
        <input type="text" class="form-control" v-model="dados.endereco" placeholder="Endereço" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="text" class="form-control" v-model="dados.cidade" placeholder="Cidade" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <label class="form-label" for="estado">Estado:</label>
        <select class="form-select" id="estado" v-model="dados.estado">
          <option v-for="estado of estados" :key="estado">{{ estado.name }}</option>
        </select>
      </div>

      <!-- HOBBIES  -->
      <section class="separar">
        <p>Seus Hobbies:</p>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="checkbox" id="esportes" v-model="dados.hobbies" value="esportes"/>
          <label class="form-check-label" for="esportes">Esportes</label>
        </div>
        <div class="form-check form-check-inline" >
          <input class="form-check-input" type="checkbox" id="musica" v-model="dados.hobbies" value="musica" />
          <label class="form-check-label" for="musica">Música</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="checkbox" id="leitura" v-model="dados.hobbies" value="leitura" />
          <label class="form-check-label" for="leitura">Leitura</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="checkbox" id="filme" v-model="dados.hobbies" value="filme" />
          <label class="form-check-label" for="filme">Filmes/Seriados</label>
        </div>
      </section>
      <!-- LINGUAGENS DE PROGRAMAÇÂO -->
      <section class="separar">
        <p>Linguagem preferida:</p>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" id="js" value="js" v-model="dados.linguagens"/>
          <label class="form-check-label" for="js">JavaScript</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" id="swift" value="swift" v-model="dados.linguagens" />
          <label class="form-check-label" for="pyton">Swift</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" id="php" value="php" v-model="dados.linguagens"/>
          <label class="form-check-label" for="php">PHP</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="radio" id="c" value="c" v-model="dados.linguagens"/>
          <label class="form-check-label" for="c">C</label>
        </div>
      </section>

      <!-- BIOGRAFIA -->
      <div data-mdb-input-init class="form-outline mb-4">
        <textarea class="form-control" id="form6Example7" rows="4" placeholder="Biografia" v-model="dados.bio"></textarea>
      </div>

      <!-- ENVIAR -->
      <button @click="enviar = false" data-mdb-ripple-init type="button"
        class="btn btn-primary btn-block mb-4">Enviar</button>
    </form>
    <section v-else>
      <div>
        <h2>Dados:</h2>
        <p>Nome: {{ dados.nome }}</p>
        <p>Sobrenome: {{ dados.sobrenome }}</p>
        <p>E-mail: {{ dados.email }}</p>
        <p>Senha: {{ dados.senha }}</p>
        <p>Endereço: {{ dados.endereco }}</p>
        <p>Cidade: {{ dados.cidade }}</p>
        <p>Estados: {{ dados.estado }}</p>
        <p>Hobbies: {{ dados.hobbies }}</p>
        <p>Linguagem favorita: {{ dados.linguagens }}</p>
        <p>Biografia: {{ dados.bio }}</p>
      </div>

      <button @click="enviar = true" data-mdb-ripple-init type="button"
        class="btn btn-primary btn-block mb-4">Voltar</button>
    </section>
  </main>
</template>

<style scoped>
main {
  margin-left: 50%;
  width: 70%;
}

.separar {
  margin-top: 5%;
  margin-bottom: 5%;
}

form {
  margin-top: 10%;
}
</style>
