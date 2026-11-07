
<script setup>
import { onMounted, onUnmounted } from 'vue'

const emit = defineEmits(['fechar'])

const hobbies = [
  {
    id: 1,
    icone: '⚽',
    nome: 'Futebol',
    descricao: 'Gosto de acompanhar e praticar futebol.'
  },
  {
    id: 2,
    icone: '💻',
    nome: 'Tecnologia e inovação',
    descricao: 'Gosto de explorar novas tecnologias e acompanhar a inovação.'
  },
  {
    id: 3,
    icone: '🎮',
    nome: 'Jogos digitais',
    descricao: 'Nos tempos livres, gosto de jogar videojogos.'
  },
  {
    id: 4,
    icone: '🎬',
    nome: 'Cinema e séries',
    descricao: 'Gosto de assistir a filmes e séries.'
  }
]

function fecharComEscape(evento) {
  if (evento.key === 'Escape') {
    emit('fechar')
  }
}

onMounted(() => {
  window.addEventListener('keydown', fecharComEscape)
})

onUnmounted(() => {
  window.removeEventListener('keydown', fecharComEscape)
})
</script>

<template>
  <div
    class="modal-fundo"
    @click.self="emit('fechar')"
  >
    <section
      class="modal-hobbies"
      role="dialog"
      aria-modal="true"
      aria-labelledby="titulo-hobbies"
    >
      <div class="conteudo-hobbies">
        <button
          type="button"
          class="fechar-hobbies"
          aria-label="Fechar janela"
          @click="emit('fechar')"
        >
          &times;
        </button>

        <h2 id="titulo-hobbies">Hobbies</h2>

        <div class="grelha-hobbies">
          <article
            v-for="hobby in hobbies"
            :key="hobby.id"
            class="cartao-hobby"
          >
            <span class="icone-hobby" aria-hidden="true">
              {{ hobby.icone }}
            </span>

            <h3>{{ hobby.nome }}</h3>

            <p>{{ hobby.descricao }}</p>
          </article>
        </div>
      </div>
    </section>
  </div>
</template>
