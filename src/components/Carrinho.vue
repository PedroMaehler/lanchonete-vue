<!-- PARTE 4 -->
<script setup>
import { ref } from 'vue'

const itens = ref([])
const texto = ref('')

// #25 - Adicionar
// Em React: setItens([...itens, novo])  (o React precisa de um array NOVO)
function adicionar() {
  if (texto.value.trim() === '') return
  const novo = { id: Date.now(), texto: texto.value, entregue: false }
  itens.value.push(novo) // em Vue o push funciona direto
  texto.value = ''
}

// #26 - Remover
// Em React: setItens(itens.filter((i) => i.id !== id))
function remover(id) {
  itens.value = itens.value.filter((i) => i.id !== id)
}

// Exercício 4: ao clicar no item, marcar como entregue (riscado, classe "entregue")
</script>

<template>
  <div class="caixa">
    <h3>#25 e #26 - Carrinho</h3>

    <form @submit.prevent="adicionar">
      <input v-model="texto" placeholder="Ex.: 2 X-Burguer" />
      <button type="submit">Adicionar</button>
    </form>

    <p v-if="itens.length === 0">Carrinho vazio.</p>

    <ul>
      <li v-for="item in itens" :key="item.id">
        {{ item.texto }}
        <button @click="remover(item.id)">Remover</button>
      </li>
    </ul>
  </div>
</template>
