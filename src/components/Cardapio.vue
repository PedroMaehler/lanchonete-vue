<!-- PARTE 2 -->
<script setup>
import { ref, computed } from 'vue'
import Cartao from './Cartao.vue'

// #8 - Os dados: um array de objetos, cada um com id
const lanches = ref([
  { id: 1, nome: 'X-Burguer', preco: 18, tipo: 'lanche', foto: 'https://picsum.photos/200?random=1', descricao: 'Pão, carne e queijo', maisPedido: true },
  { id: 2, nome: 'X-Salada', preco: 20, tipo: 'lanche', foto: 'https://picsum.photos/200?random=2', descricao: 'Pão, carne, queijo e salada', maisPedido: false },
  { id: 3, nome: 'Misto Quente', preco: 12, tipo: 'lanche', foto: 'https://picsum.photos/200?random=3', descricao: 'Pão, presunto e queijo', maisPedido: false },
  { id: 4, nome: 'Batata Frita', preco: 15, tipo: 'porcao', foto: 'https://picsum.photos/200?random=4', maisPedido: false }, // sem descrição, para o #11
  { id: 5, nome: 'Refrigerante', preco: 7, tipo: 'bebida', foto: 'https://picsum.photos/200?random=5', descricao: 'Lata 350 ml', maisPedido: false },
  { id: 6, nome: 'Suco de Laranja', preco: 9, tipo: 'bebida', foto: 'https://picsum.photos/200?random=6', descricao: 'Natural, 500 ml', maisPedido: true },
])

// #14 - Filtro com computed: recalcula sozinho quando a lista muda
// Em React: lanches.filter((l) => l.tipo === 'bebida')
const bebidas = computed(() => lanches.value.filter((l) => l.tipo === 'bebida'))

// Exercício 2: acrescentar um lanche novo no array, sem descrição,
// e ver o cartão aparecer com "Sem descrição"
</script>

<template>
  <section class="caixa">
    <h3>#8 a #13 - Cardápio</h3>
    <div class="grade">
      <!-- #9 - Lista: v-for com :key · #10 - Props: cada :nome, :preco... entrega um dado ao Cartao -->
      <!-- Em React: {lanches.map((l) => <Cartao key={l.id} ... />)} -->
      <Cartao
        v-for="lanche in lanches"
        :key="lanche.id"
        :nome="lanche.nome"
        :preco="lanche.preco"
        :foto="lanche.foto"
        :descricao="lanche.descricao"
        :mais-pedido="lanche.maisPedido"
      />
    </div>
  </section>

  <section class="caixa">
    <h3>#14 - Só bebidas</h3>
    <div class="grade">
      <Cartao
        v-for="bebida in bebidas"
        :key="bebida.id"
        :nome="bebida.nome"
        :preco="bebida.preco"
        :foto="bebida.foto"
        :descricao="bebida.descricao"
        :mais-pedido="bebida.maisPedido"
      />
    </div>
  </section>
</template>
