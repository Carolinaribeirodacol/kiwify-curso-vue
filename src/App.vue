<script setup>
import { ref, reactive } from 'vue'

const person = ref({
  name: 'John Doe',
  age: 30
})

const state = reactive({
  count: 0
})
// const count = ref(0)
// console.log(count.value)
</script>

<template>
  <!-- <div>{{ count }}</div> -->
  <div>{{ state.count }}</div>
  <input type="text" v-model="person.name"/>
  <button @click="count++">Increment</button>

  <p>Ref precisa acessar com .value dentro do script</p>
  <p>Reactive é para objetos ou arrays</p>
</template>
