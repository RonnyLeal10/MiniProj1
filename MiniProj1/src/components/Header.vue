
<template>
  <header class="cabecalho">
    <div class="perfil">
      <div class="fotografia">
        <img
          v-if="fotoDisponivel"
          src="/Ronny.jpeg"
          alt="Fotografia de perfil"
          @error="fotoDisponivel = false"
        />
        <span v-else>Foto</span>
      </div>

      <div class="identidade">
        <h1>Ronilson Leal Gomes</h1>
        <p>Engenheiro Informático</p>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const fotoDisponivel = ref(true)
</script>
