<script setup>
import { ref } from 'vue'
const litado = ref(8)

async function cargar() {
  let product = await fetch(
    'https://my-json-server.typicode.com/agustinruatta/fake_json_server_db/products/',
  )
  litado.value = await product.json()
}
cargar()
</script>

<template>
  <ul>
    <li v-for="(elemento, indice) in listado" :key="indice">{{ elemento.title }}</li>
  </ul>
</template>

<style scoped></style>
