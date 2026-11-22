<!-- #2 - Arquivo .vue: script (dados e funções), template (HTML) e style (CSS) -->

<script setup>
// PARTE 1 ==========================================
import Cabecalho from './components/Cabecalho.vue'
import Rodape from './components/Rodape.vue'

// #3 - Interpolação: variáveis mostradas com {{ }}
const nome = 'Lanchonete do Grupo'
const ano = 2026

// #4 - Estilo inline é um OBJETO
const estiloDestaque = { color: 'tomato', fontSize: '24px' }

// #5 - Atributo ligado a uma variável
const fotoFachada = 'https://picsum.photos/400/200?random=10'

// #6 - Condicional
const aberta = true
const temEntrega = false // Exercício 1

// PARTE 2 ==========================================
import Cardapio from './components/Cardapio.vue'

// PARTE 3 ==========================================
import Eventos from './components/Eventos.vue'
import ContadorErrado from './components/ContadorErrado.vue'
import Quantidade from './components/Quantidade.vue'

// PARTE 4 ==========================================
import Cliente from './components/Cliente.vue'
import Carrinho from './components/Carrinho.vue'
</script>

<template>
  <!-- #7 - Vários elementos na raiz: o template aceita mais de um elemento solto -->
  <Cabecalho />

  <main>
    <!-- AULA 1 ======================================== -->
    <h2 class="marca-aula">Aula 1: Template, componentes e props</h2>

    <!-- PARTE 1 -->
    <div class="caixa">
      <h3>#3 - Interpolação</h3>
      <!-- {{ }} mostra o valor da variável dentro do HTML -->
      <p>Bem-vindo à {{ nome }}!</p>
      <p>Estamos em {{ ano }}. Ano que vem será {{ ano + 1 }}.</p>
      <p>Em maiúsculas: {{ nome.toUpperCase() }}</p>
    </div>

    <div class="caixa">
      <h3>#4 - Classe e estilo</h3>
      <!-- class normal, como no HTML -->
      <p class="aviso">Em Vue usamos class, igual ao HTML</p>
      <!-- :style recebe o objeto estiloDestaque -->
      <p :style="estiloDestaque">Estilo inline é um objeto</p>
    </div>

    <div class="caixa">
      <h3>#5 - Atributo com dois-pontos</h3>
      <!-- :src pega o endereço da variável fotoFachada -->
      <img :src="fotoFachada" alt="Fachada da lanchonete" />
    </div>

    <div class="caixa">
      <h3>#6 - Condicional</h3>
      <!-- v-if e v-else: aparece só um dos dois -->
      <p v-if="aberta">Aberta! Faça seu pedido.</p>
      <p v-else>Fechada. Volte amanhã.</p>

      <!-- v-if sozinho: aparece só quando aberta é true -->
      <p v-if="aberta">Hoje tem promoção de batata frita.</p>

      <!-- Exercício 1: usar a variável temEntrega para mostrar só uma das frases -->
      <!-- <p>Entregamos em casa!</p> -->
      <!-- <p>Só retirada no balcão.</p> -->
    </div>

    <!-- PARTE 2 -->
    <Cardapio />

    <!-- AULA 2 ======================================== -->
    <h2 class="marca-aula">Aula 2: Eventos, estado e formulário</h2>

    <!-- PARTE 3 -->
    <Eventos />
    <ContadorErrado />

    <!-- #19 - Dois componentes iguais: cada um tem o seu próprio estado -->
    <h3>#19 - Cada quantidade tem o seu próprio estado</h3>
    <div class="lado-a-lado">
      <Quantidade />
      <Quantidade />
    </div>

    <!-- PARTE 4 -->
    <Cliente />
    <Carrinho />
  </main>

  <Rodape />
</template>
