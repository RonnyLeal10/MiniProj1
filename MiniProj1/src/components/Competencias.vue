

<script setup>
const competencias = [
  {
    id: 1,
    nome: 'Desenvolvimento Web',
    tecnologias: 'HTML, CSS, JavaScript e Vue.js',
    icone: '💻',
    cor: 'web'
  },
  {
    id: 2,
    nome: 'Programação',
    tecnologias: 'Python e JavaScript',
    icone: '⌨️',
    cor: 'programacao'
  },
  {
    id: 3,
    nome: 'Cloud e Integração',
    tecnologias: 'Azure Functions e APIs',
    icone: '☁️',
    cor: 'cloud'
  },
  {
    id: 4,
    nome: 'IoT e Sistemas',
    tecnologias: 'Sensores e dispositivos conectados',
    icone: '⚙️',
    cor: 'iot'
  }
]
</script>

<template>
  <section class="competencias" aria-labelledby="titulo-competencias">
    <h2 id="titulo-competencias">COMPETÊNCIAS</h2>

    <div class="lista-competencias">
      <article
        v-for="competencia in competencias"
        :key="competencia.id"
        class="competencia-cartao"
      >
        <div class="competencia-info">
          <span class="competencia-icone" aria-hidden="true">
            {{ competencia.icone }}
          </span>

          <div>
            <h3>{{ competencia.nome }}</h3>
            <p>{{ competencia.tecnologias }}</p>
          </div>
        </div>

        <div
          class="competencia-barra"
          aria-hidden="true"
        >
          <div
            class="competencia-progresso"
            :class="competencia.cor"
          ></div>
        </div>
      </article>
    </div>
  </section>
</template>
