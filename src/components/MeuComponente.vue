<template>
  <h2>Meu componente - Usuário {{ usuario }}</h2>
</template>

<script setup>
import { onBeforeMount, onMounted, onUpdated, ref, onBeforeUnmount, onUnmounted } from 'vue';
const id = ref('1234')
const usuario = ref('')

function requestFake() {
  setTimeout(() => {
    usuario.value = 'John Doe'
  }, 2000);
}

onBeforeMount(() => {
  console.log('onBeforeMounted')
})

onMounted(() => {
  console.log('onMounted')
  if (id.value) {
    requestFake()
  }
})

onUpdated(() => {
  console.log('onUpdated')
})

onBeforeUnmount(() => {
  console.log('onBeforeUnmount')
})

onUnmounted(() => {
  console.log('onUnmounted')
})
</script>
