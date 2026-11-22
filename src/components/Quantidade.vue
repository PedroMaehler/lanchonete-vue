<!-- PARTE 3 -->
<script setup>
import { ref } from 'vue'

// #18 - Jeito CERTO: ref
// Em React: const [quantidade, setQuantidade] = useState(0)
const quantidade = ref(0)
const estoque = 5

function somar() {
  quantidade.value = quantidade.value + 1 // no script usa .value
}

// Exercício 3:
// - botão para diminuir (sem passar de 0)
// - botão para zerar
// - mostrar "Pedido grande!" quando passar de 9
</script>

<template>
  <div class="caixa">
    <h3>#18 e #20 - Quantidade com ref</h3>
    <!-- #20 - Classe reativa: vermelho quando passa do estoque -->
    <!-- Em React: className={quantidade > estoque ? 'alerta' : ''} -->
    <p :class="{ alerta: quantidade > estoque }">Quantidade: {{ quantidade }}</p>
    <p>Estoque: {{ estoque }}</p>
    <button @click="somar">+1</button>
  </div>
</template>
