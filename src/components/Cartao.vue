<!-- PARTE 2 -->
<script setup>
// #10 - Props: os dados que o pai passa para o filho
// defineProps lista os dados que o Cartao recebe
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
  <!-- :class liga cartao-destaque só quando maisPedido é true -->
  <div class="cartao" :class="{ 'cartao-destaque': maisPedido }">
    <img :src="foto" :alt="nome" />
    <h3>{{ nome }}</h3>
    <p>{{ descricao }}</p>
    <p class="preco">R$ {{ preco }}</p>
    <!-- #13 - Selo com v-if: aparece só no mais pedido -->
    <!-- v-if: o selo só existe quando maisPedido é true -->
    <span v-if="maisPedido" class="selo">Mais pedido</span>
  </div>
</template>
