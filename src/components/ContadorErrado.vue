<!-- PARTE 3 -->
<script setup>

// #17 - Jeito ERRADO: variável comum, o valor muda (F12) mas a tela não atualiza
let quantidade = 0

function somar() {
  quantidade = quantidade + 1
  console.log('quantidade =', quantidade)
}
</script>

<template>
  <div class="caixa">
    <h3>#17 - Variável comum (não funciona)</h3>
    <p>Quantidade: {{ quantidade }}</p>
    <button @click="somar">+1</button>
  </div>
</template>
