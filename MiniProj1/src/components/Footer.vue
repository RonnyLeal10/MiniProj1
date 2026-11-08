

<script setup>
import {
  Instagram,
  Facebook,
  Github,
  Mail,
  MessageCircle
} from 'lucide-vue-next'

const contactos = [
  {
    nome: 'Instagram',
    url: 'https://www.instagram.com/ronnygomes720/',
    icone: Instagram
  },
  {
    nome: 'Facebook',
    url: 'https://www.facebook.com/share/19K3NLB3zC/',
    icone: Facebook
  },
  {
    nome: 'GitHub',
    url: 'https://github.com/RonnyLeal10',
    icone: Github
  },
  {
    nome: 'WhatsApp',
    url: 'https://wa.me/351925717227',
    icone: MessageCircle
  },
  {
    nome: 'Email',
    url: 'mailto:Wrnlealgomes100@gamil.com',
    icone: Mail
  }
]
</script>

<template>
  <footer class="rodape">
    <div class="contactos">
      <a
        v-for="contacto in contactos"
        :key="contacto.nome"
        :href="contacto.url"
        :target="contacto.nome === 'Email' ? undefined : '_blank'"
        :rel="contacto.nome === 'Email' ? undefined : 'noopener noreferrer'"
        :aria-label="contacto.nome"
        :title="contacto.nome"
        class="contacto-link"
      >
        <component
          :is="contacto.icone"
          :size="24"
          :stroke-width="2"
          aria-hidden="true"
        />

        <span>{{ contacto.nome }}</span>
      </a>
    </div>
  </footer>
</template>

