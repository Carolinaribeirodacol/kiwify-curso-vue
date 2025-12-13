<script setup>
import { ref , watch, watchEffect } from 'vue'

const inputName = ref('')
const usuario = ref('')
const data = ref(null)

function setName() {
  usuario.value = inputName.value
}

watch(usuario, (newValue, oldValue) => {
  console.log('Valor antigo', oldValue)
  console.log('Valor novo', newValue)
})

watchEffect(async () => {
  const response = await fetch(`https://jsonplaceholder.typicode.com/todos/${usuario.value}`)

  data.value = await response.json()
  console.log(response)
})
</script>

<template>
  <div>
    <input type="text" v-model="inputName">
    <button @click="setName">Enviar nome</button>
  </div>
</template>
