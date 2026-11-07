
<script setup>
import { onMounted, onUnmounted } from 'vue'

// Evento para fechar a janela
const emit = defineEmits(['fechar'])

// EXPERIÊNCIAS PROFISSIONAIS
const experiencias = [
  {
    id: 1,
    cargo: 'Bolsa de Colaboração em Engenharia Informática',
    local: 'ESTGL - IPV',
    periodo: '2024 – 2025',
    descricao:
      'Configuração de servidores e manutenção de sistemas informáticos.'
  },
  {
    id: 2,
    cargo: 'Colaborador',
    local: 'Burger King',
    periodo: '01/2026 – 07/2026',
    descricao:
      'Preparação de alimentos, atendimento ao cliente e manutenção da limpeza do espaço.'
  }
]

// PROJETOS REALIZADOS
const projetos = [
  {
    id: 1,
    titulo: 'Azure Functions — Números Primos',
    categoria: 'Computação na nuvem',
    descricao:
      'Projeto académico que utiliza Azure Functions para calcular números primos através de pedidos HTTP.'
  },
  {
    id: 2,
    titulo: 'Sistema de localização Indoor',
    categoria: 'Aplicações Web',
    descricao:
      'Desenvolvimento do sistema capaz de mostrar a localização indoor utilizando Esp32 como beacon e aplicação feito em flutter.'
  },
  {
    id: 3,
    titulo: 'Frigorifico inteligente',
    categoria: 'Internet das Coisas',
    descricao:
      'Utilização de sensores e microcontroladores como Esp32 e Raspberry Pi 4 para monitorizar a temperatura e humidade de um frigorífico, enviando os dados para uma aplicação web. Tambem foi utilizado sersor magnetico e ventoinha'
  }
]

// Fechar a janela com a tecla Escape
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
  <!-- Fundo escurecido -->
  <div
    class="modal-fundo"
    @click.self="emit('fechar')"
  >
    <!-- Janela principal -->
    <section
      class="modal-faco"
      role="dialog"
      aria-modal="true"
      aria-labelledby="titulo-faco"
    >
      <!-- Botão fechar -->
      <button
        class="fechar-faco"
        type="button"
        aria-label="Fechar janela"
        @click="emit('fechar')"
      >
        &times;
      </button>

      <!-- Título -->
      <h2 id="titulo-faco">O que faço?</h2>

      <p class="introducao-faco">
        Conhece as minhas experiências profissionais
        e alguns dos projetos que desenvolvi
        durante o meu percurso académico.
      </p>

      <!-- =========================
           EXPERIÊNCIAS PROFISSIONAIS
      ========================== -->
      <h3 class="titulo-secao-faco">
        Experiências profissionais
      </h3>

      <div class="timeline">
        <article
          v-for="experiencia in experiencias"
          :key="experiencia.id"
          class="timeline-item"
        >
          <span
            class="timeline-ponto"
            aria-hidden="true"
          ></span>

          <div class="timeline-conteudo">
            <h3>{{ experiencia.cargo }}</h3>

            <span class="categoria-projeto">
              {{ experiencia.local }}
              | {{ experiencia.periodo }}
            </span>

            <p>{{ experiencia.descricao }}</p>
          </div>
        </article>
      </div>

      <!-- =========================
           PROJETOS REALIZADOS
      ========================== -->
      <h3 class="titulo-secao-faco">
        Projetos realizados
      </h3>

      <div class="timeline">
        <article
          v-for="projeto in projetos"
          :key="projeto.id"
          class="timeline-item"
        >
          <span
            class="timeline-ponto"
            aria-hidden="true"
          ></span>

          <div class="timeline-conteudo">
            <h3>{{ projeto.titulo }}</h3>

            <span class="categoria-projeto">
              {{ projeto.categoria }}
            </span>

            <p>{{ projeto.descricao }}</p>
          </div>
        </article>
      </div>

    </section>
  </div>
</template>
