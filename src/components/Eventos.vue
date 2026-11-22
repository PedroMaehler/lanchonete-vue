<!-- PARTE 3 -->
<script setup>
// #15 - Evento: o botão chama uma função com nome
// o @click do botão chama esta função pelo nome
function chamarGarcom() {
  alert('O garçom já está indo!')
}

// #16 - Evento com argumento
// o @click passa o nome do lanche como argumento
function pedir(lanche) {
  alert('Você pediu: ' + lanche)
}
</script>

<template>
  <div class="caixa">
    <h3>#15 e #16 - Eventos</h3>
    <button @click="chamarGarcom">Chamar garçom</button>
    <button @click="pedir('X-Burguer')">Pedir X-Burguer</button>
    <button @click="pedir('Suco de Laranja')">Pedir Suco</button>
  </div>
</template>
