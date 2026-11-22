<!-- PARTE 4 -->
<script setup>
import { ref } from 'vue'

const nome = ref('')
const enviado = ref('')

// #23 - Envio: o .prevent no template impede a página de recarregar
// confirmar guarda o nome enviado e limpa o campo
function confirmar() {
  if (nome.value.trim() === '') return
  enviado.value = nome.value
  nome.value = '' // limpa o campo
}
</script>

<template>
  <!-- @submit.prevent chama confirmar sem recarregar a página -->
  <form class="caixa" @submit.prevent="confirmar">
    <h3>#21 a #24 - Nome do cliente</h3>
    <label for="nome">Seu nome: </label>

    <!-- #21 - v-model: liga o campo à variável nos dois sentidos -->
    <!-- o que for digitado vai direto para a variável nome -->
    <input id="nome" v-model="nome" placeholder="Digite seu nome" />
    <button type="submit">Confirmar</button>

    <!-- #22 - Muda enquanto digita -->
    <p>Digitando: {{ nome }}</p>
    <p>Tamanho: {{ nome.length }} caracteres</p>

    <!-- #24 - Aparece só depois do envio -->
    <!-- v-if: só aparece depois que enviado recebe um nome -->
    <h3 v-if="enviado">Pedido de: {{ enviado }}</h3>
  </form>
</template>
