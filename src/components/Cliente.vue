<!-- PARTE 4 -->
<script setup>
import { ref } from 'vue'

const nome = ref('')
const enviado = ref('')

// #23 - Envio: o .prevent no template impede a página de recarregar
// Em React: function handleSubmit(e) { e.preventDefault(); ... }
function confirmar() {
  if (nome.value.trim() === '') return
  enviado.value = nome.value
  nome.value = '' // limpa o campo
}
</script>

<template>
  <!-- Em React: <form onSubmit={handleSubmit}> -->
  <form class="caixa" @submit.prevent="confirmar">
    <h3>#21 a #24 - Nome do cliente</h3>
    <label for="nome">Seu nome: </label>

    <!-- #21 - v-model: liga o campo à variável nos dois sentidos -->
    <!-- Em React: value={nome} onChange={(e) => setNome(e.target.value)} -->
    <input id="nome" v-model="nome" placeholder="Digite seu nome" />
    <button type="submit">Confirmar</button>

    <!-- #22 - Muda enquanto digita -->
    <p>Digitando: {{ nome }}</p>
    <p>Tamanho: {{ nome.length }} caracteres</p>

    <!-- #24 - Aparece só depois do envio -->
    <!-- Em React: {enviado && <h3>...</h3>} -->
    <h3 v-if="enviado">Pedido de: {{ enviado }}</h3>
  </form>
</template>
