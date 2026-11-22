<!-- PARTE 2 -->
<script setup>

// #10 - Props: os dados que o pai passa para o filho
defineProps({
  nome: String,
  preco: Number,
  foto: String,
  descricao: { type: String, default: 'Sem descrição' }, // #11 - Valor padrão
  maisPedido: Boolean,
})
</script>

<template>

  <!-- #12 - Classe condicional: borda dourada no mais pedido -->
  <div class="cartao" :class="{ 'cartao-destaque': maisPedido }">
    <img :src="foto" :alt="nome" />
    <h3>{{ nome }}</h3>
    <p>{{ descricao }}</p>
    <p class="preco">R$ {{ preco }}</p>

    <!-- #13 - Selo com v-if: aparece só no mais pedido -->
    <span v-if="maisPedido" class="selo">Mais pedido</span>
  </div>
</template>
