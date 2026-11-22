<!-- PARTE 1 - #7 - Componente com uma variável própria -->
<script setup>
const anoAtual = new Date().getFullYear()
</script>

<template>
  <footer class="rodape">
    <p>© {{ anoAtual }} - Feito com Vue por João Paulo, Edson, João Vítor e Pedro</p>
  </footer>
</template>
