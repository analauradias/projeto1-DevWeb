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
</script>

<template>
  <form>
    <div class="row mb-4">
      <div class="col">
        <div data-mdb-input-init class="form-outline">
          <input type="text" class="form-control" v-model="dados.nome" placeholder="Nome" />
        </div>
      </div>

      <div class="col">
        <div data-mdb-input-init class="form-outline">
          <input
            type="text"
            class="form-control"
            v-model="dados.sobrenome"
            placeholder="Sobrenome"
          />
        </div>
      </div>
    </div>

    <!-- Text input -->
    <div data-mdb-input-init class="form-outline mb-4">
      <input type="email" class="form-control" v-model="dados.email" placeholder="E-mail" />
    </div>

    <!-- Text input -->
    <div data-mdb-input-init class="form-outline mb-4">
      <input type="password" class="form-control" v-model="dados.senha" placeholder="Senha" />
    </div>

    <!-- Email input -->
    <div data-mdb-input-init class="form-outline mb-4">
      <input
        type="password"
        class="form-control"
        v-model="dados.confirmSenha"
        placeholder="Confirme sua senha"
      />
    </div>

    <!-- Number input -->
    <div data-mdb-input-init class="form-outline mb-4">
      <input
        type="date"
        class="form-control"
        v-model="dados.dataNasc"
        placeholder="Data de nascimento"
      />
    </div>

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
        <input class="form-check-input" type="checkbox" id="esportes" value="option1" />
        <label class="form-check-label" for="esportes">Esportes</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" id="musica" value="option2" />
        <label class="form-check-label" for="musica">Música</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" id="leitura" value="option2" />
        <label class="form-check-label" for="leitura">Leitura</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="checkbox" id="filme" value="option2" />
        <label class="form-check-label" for="filme">Filmes/Seriados</label>
      </div>
    </section>
    <!-- LINGUAGENS DE PROGRAMAÇÂO -->
    <section class="separar">
      <p>Linguagem preferida:</p>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="js" value="option1" />
        <label class="form-check-label" for="js">JavaScript</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="pyton" value="option2" />
        <label class="form-check-label" for="pyton">Pyton</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="php" value="option2" />
        <label class="form-check-label" for="php">PHP</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="c" value="option2" />
        <label class="form-check-label" for="c">C</label>
      </div>
    </section>

    <!-- Message input -->
    <div data-mdb-input-init class="form-outline mb-4">
      <textarea class="form-control" id="form6Example7" rows="4"></textarea>
      <label class="form-label" for="form6Example7">Additional information</label>
    </div>

    <!-- Checkbox -->
    <div class="form-check d-flex justify-content-center mb-4">
      <input class="form-check-input me-2" type="checkbox" value="" id="form6Example8" checked />
      <label class="form-check-label" for="form6Example8"> Create an account? </label>
    </div>

    <!-- Submit button -->
    <button data-mdb-ripple-init type="button" class="btn btn-primary btn-block mb-4">
      Place order
    </button>
  </form>
</template>

<style scoped>
.separar {
  margin-top: 5%;
}
</style>
