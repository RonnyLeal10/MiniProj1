
<script setup>
import { ref } from 'vue'

import Header from './components/Header.vue'
import Navigation from './components/Navigation.vue'
import Competencias from './components/Competencias.vue'
import Footer from './components/Footer.vue'
import QuemSou from './components/QuemSou.vue'
import OQueFaco from './components/OqueFaco.vue'
import Hobbies from './components/Hobbies.vue'

const modalAtivo = ref(null)

function abrirModal(secao) {
  modalAtivo.value = secao
}

function fecharModal() {
  modalAtivo.value = null
}
</script>

<template>
  <div class="pagina">
    <Header />

    <Navigation @abrir-modal="abrirModal" />

    <Competencias />

    <Footer />

    <QuemSou
      v-if="modalAtivo === 'quem'"
      @fechar="fecharModal"
    />

    <OQueFaco
      v-if="modalAtivo === 'faco'"
      @fechar="fecharModal"
    />

    <Hobbies
      v-if="modalAtivo === 'hobbies'"
      @fechar="fecharModal"
    />
  </div>
</template>
