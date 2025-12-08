<script setup>
  const modulo = 'Módulo 2'
  const nomeDoAluno = '<span style="color: red">Lucas</span>'
  const btnDisabled = false

  const atributos = {
    style: 'color: blue',
    id: 'titulo-principal',
    class: 'titulo-color'
  }
</script>

<template>
  <h1 :v-bind="atributos" :title="modulo">Curso vuejs expert - {{ modulo }}</h1>
  <p v-html="nomeDoAluno"></p>
  <button :disabled="btnDisabled">Salvar</button>
</template>

<style scoped>

</style>
