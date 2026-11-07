
<script setup>
defineEmits(['fechar'])
</script>

<template>
  <div class="modal-fundo" @click.self="$emit('fechar')">
    <section
      class="modal-quem"
      role="dialog"
      aria-modal="true"
      aria-labelledby="titulo-quem"
    >
      <button
        class="fechar-modal"
        aria-label="Fechar janela"
        @click="$emit('fechar')"
      >
        ×
      </button>

      <div class="conteudo-quem">
        <h2 id="titulo-quem">Quem Sou Eu?</h2>

        <h3>Sobre mim</h3>
        <p>
          Licenciado em Engenharia Informática e
          Telecomunicações e atualmente frequento o
          Mestrado em Engenharia Informática e Tecnologia Web.
        </p>

        <hr />

        <h3>Informações pessoais</h3>
        <p>Nacionalidade: Guineense e Portuguesa</p>
        <p>Área: Engenharia Informática</p>

        <hr />

        <h3>Formação académica</h3>
        <p>
          <strong>Mestrado em Engenharia Informática
          e Tecnologia Web</strong>
          — UTAD
        </p>
        <p>
          <strong>Licenciatura em Engenharia Informática
          e Telecomunicações</strong>
          — Instituto Politécnico de Viseu
        </p>
      </div>
    </section>
  </div>
</template>
