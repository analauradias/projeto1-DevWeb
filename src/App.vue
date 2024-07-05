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

const enviar = ref(true)
</script>

<template>
  <main>
    <form v-if="enviar">
      <h1>Crie seu perfil</h1>
      <div class="row mb-4">
        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input type="text" class="form-control" v-model="dados.nome" placeholder="Nome" required/>
          </div>
        </div>

        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input
              type="text"
              class="form-control"
              v-model="dados.sobrenome"
              placeholder="Sobrenome"
              required
            />
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
        <input
          type="password"
          class="form-control"
          v-model="dados.confirmSenha"
          placeholder="Confirme sua senha"
        />
      </div>

      <!-- DATA DE NASCIMENTO -->
      <div data-mdb-input-init class="form-outline mb-4">
        <label for="dataNasc">Data de nascimento:</label>
        <input
          type="date"
          id="dataNasc"
          class="form-control"
          v-model="dados.dataNasc"
          placeholder="Data de nascimento"
        />
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
          <input
            class="form-check-input"
            type="checkbox"
            id="esportes"
            v-model="dados.hobbies"
            value="esportes"
          />
          <label class="form-check-label" for="esportes">Esportes</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="música"
            v-model="dados.hobbies"
            value="musica"
          />
          <label class="form-check-label" for="musica">Música</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="leitura"
            v-model="dados.hobbies"
            value="leitura"
          />
          <label class="form-check-label" for="leitura">Leitura</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="checkbox"
            id="filme"
            v-model="dados.hobbies"
            value="filme"
          />
          <label class="form-check-label" for="filme">Filmes/Seriados</label>
        </div>
      </section>
      <!-- LINGUAGENS DE PROGRAMAÇÂO -->
      <section class="separar">
        <p>Linguagem preferida:</p>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="js"
            value="JS"
            v-model="dados.linguagens"
          />
          <label class="form-check-label" for="js">JavaScript</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="swift"
            value="Swift"
            v-model="dados.linguagens"
          />
          <label class="form-check-label" for="pyton">Swift</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="php"
            value="Php"
            v-model="dados.linguagens"
          />
          <label class="form-check-label" for="php">PHP</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            id="c"
            value="C"
            v-model="dados.linguagens"
          />
          <label class="form-check-label" for="c">C</label>
        </div>
      </section>

      <!-- BIOGRAFIA -->
      <div data-mdb-input-init class="form-outline mb-4">
        <textarea
          class="form-control"
          id="form6Example7"
          rows="4"
          placeholder="Biografia"
          v-model="dados.bio"
        ></textarea>
      </div>

      <!-- ENVIAR -->
      <button
        @click="enviar = false"
        data-mdb-ripple-init
        type="submit"
        class="btn btn-primary btn-block mb-4"
        v-if="dados.senha === dados.confirmSenha && dados.nome != '' && dados.sobrenome != '' && dados.email != ''"
      >
        Enviar
      </button>
    </form>
    <section v-else>
      <div >
        <h1 style="text-align: center; margin-bottom: 20px;">Dados</h1>
        <p><strong>Nome:</strong> {{ dados.nome }}</p>
        <p><strong>Sobrenome:</strong> {{ dados.sobrenome }}</p>
        <p><strong>E-mail:</strong> {{ dados.email }}</p>
        <p><strong>Senha:</strong> {{ dados.senha }}</p>
        <p><strong>Endereço:</strong> {{ dados.endereco }}</p>
        <p><strong>Cidade:</strong> {{ dados.cidade }}</p>
        <p><strong>Estado::</strong> {{ dados.estado }}</p>
        <p><strong>Hobbies:</strong> {{ dados.hobbies }}</p>
        <p><strong>Linguagem favorita:</strong> {{ dados.linguagens }}</p>
        <p><strong>Biografia:</strong> {{ dados.bio }}</p>
      </div>

      <button
        @click="enviar = true"
        data-mdb-ripple-init
        type="submit"
        class="btn btn-primary btn-block mb-4"
      >
        Voltar
      </button>
    </section>
  </main>
</template>

<style scoped>

main {
  margin-left: 50%;
  width: 80%;
}

.separar {
  margin-top: 5%;
  margin-bottom: 5%;
}

form {
  margin-top: 10%;
}
</style>
