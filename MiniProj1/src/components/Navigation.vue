
<template>
  <nav class="navegacao" aria-label="Navegação principal">
    <button class="botao oval" @click="abrir('quem')">
      Quem sou?
    </button>

    <button class="botao quadrado" @click="abrir('faco')">
      O que faço?
    </button>

    <button class="botao losango" @click="abrir('hobbies')">
      <span>Hobbies</span>
    </button>
  </nav>
</template>

<script setup>
const emit = defineEmits(['abrir-modal'])

function abrir(secao) {
  emit('abrir-modal', secao)
}
</script>
