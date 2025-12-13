<script setup>
import { computed, reactive, ref, onMounted } from 'vue'
import MeuComponente from './components/MeuComponente.vue'

const mentor = reactive({
  nome: 'John Doe',
  modulos: [
    'Modulo 1',
    'Modulo 2',
    'Modulo 3'
  ]
})

const mentor2 = ref({
  nome: 'John Doe',
  modulos: []
})

const possuiModulos = computed(() => {
  return mentor.modulos.length > 0
})

const possuiModulos2 = computed(() => {
  return mentor2.value.modulos.length > 0
})

const mostrarComponente = ref(false)

onMounted(() => {
  console.log('onMounted PAI')
})
</script>

<template>
<div>
  <h3>mentor: {{ mentor.nome }}</h3>
  <p>
    Possui módulos ativos: {{ possuiModulos }}
  </p>

  <h3>mentor2: {{ mentor2.nome }}</h3>
  <p>
    Possui módulos ativos: {{ possuiModulos2 }}
  </p>

  <button @click="mostrarComponente = !mostrarComponente">Mostrar componente</button>
  <MeuComponente v-if="mostrarComponente"/>
</div>
</template>
