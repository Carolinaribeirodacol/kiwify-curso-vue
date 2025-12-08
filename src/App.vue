<script setup>
import { ref } from 'vue'
const message = 'Hello Vue!'
const meuHtml = '<h1>Meu HTML</h1>'
const showElement = true
const ifElement = true
const listaDeNomes = ['Fulano', 'Ciclano', 'Beltrano']
const divClass = 'minha-classe'
const divClass2 = 'minha-classe-2'
const minhaClasse = ref(false)
const meuNome = ref('')
const idade = ref(null)

function clickHandler() {
  alert('Clicou no botão')
}

function submitForm() {
  alert('Submeteu o formulário')
}

setTimeout(() => {
  meuNome.value = 'Carolina Ribeiro'
}, 5000)
</script>

<template>
  <div>
    <div>
      <h3>v-text</h3>
      <p v-text="message"></p>
    </div>

    <div>
      <h3>v-html</h3>
      <p v-html="meuHtml"></p>
    </div>

    <div>
      <h3>v-show</h3>
      <p v-show="showElement">Elemento exibido no v-show</p>
    </div>

    <div>
      <h3>v-if</h3>
      <p v-if="ifElement">Elemento exibido no v-if</p>
      <p v-else>Elemento exibido no v-else</p>
    </div>

    <div>
      <h3>v-for</h3>
      <p v-for="nome in listaDeNomes" :key="nome"> {{ nome }} </p>
    </div>

    <div>
      <h3>v-on</h3>
      <button v-on:click="clickHandler">Clique aqui</button>
      <button @click="clickHandler">Clique aqui</button>
    </div>

    <div>
      <h3>form</h3>
      <button @click="clickHandler">Meu click</button>
      <form @submit.prevent="submitForm">
        <input type="text" placeholder="Digite algo" @keyup.enter="submitForm">
        <button type="submit">Submeter o formulário</button>
      </form>
    </div>

    <div>
      <h3>v-bind == :</h3>
      <div :class="minhaClasse ? divClass : divClass2">
        Evento com classe dinâmica v-bind
      </div>
      <button @click="minhaClasse = !minhaClasse">Mudar de classe</button>
    </div>

    <div>
      <h3>v-model</h3>
      <input type="text" v-model.trim="meuNome"> {{ meuNome }}
      <p>o trim remove espaços a mais desnecessários</p>
      <input type="tel" v-model.number="idade"> {{ typeof idade }}
    </div>

    <div>
      <h3>v-pre</h3>
      <p v-pre>{ meuNome }</p>
      <p>o v-pre ignora a compilação do vue e mostra a forma original com tags, etc</p>
    </div>

    <div>
      <h3>v-once</h3>
      <p v-once>{{ meuNome }}</p>
      <p>o v-once renderiza apenas uma vez, transforma em um dado estático se usar com algo reativo</p>
    </div>
  </div>
</template>

<style scoped>
.minha-classe {
  border: solid 1px blue;
}

.minha-classe-2 {
  border: solid 1px green;
}
</style>
