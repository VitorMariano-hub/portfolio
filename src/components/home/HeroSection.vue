<template>
  <section class="min-h-screen flex items-center justify-center pt-16">
    <div class="container mx-auto px-4 grid md:grid-cols-2 gap-8 items-center">
      <div>
        <h2 class="text-5xl font-bold mb-4">
          Olá! Meu nome é
          <span class="text-[#39FF14]">{{ name }}</span>
          e sou um desenvolvedor web full-stack
        </h2>
        <p class="text-xl mb-6">{{ role }}</p>
        <div class="flex gap-4">
          <a href="#contact" class="bg-[#39FF14] text-black px-6 py-2 rounded hover:bg-[#00FFFF] transition-colors">
            Contato
          </a>
          <a href="#projects" class="border border-[#39FF14] px-6 py-2 rounded hover:bg-[#39FF14] hover:text-black transition-colors">
            Projetos
          </a>
        </div>
        <div class="flex gap-4 mt-8">
          <a 
            v-for="social in socials" 
            :key="social.name"
            :href="social.url"
            target="_blank"
            class="hover:text-[#39FF14]"
          >
            <component :is="social.icon" class="w-6 h-6"/>
          </a>
        </div>
      </div>
      <div class="relative">
        <div class="bg-[#2C2C2C] w-64 h-64 rounded-full mx-auto relative overflow-hidden border-4 border-[#C0C0C0]">
          <img :src="profileImage" alt="Profile" class="w-full h-full object-cover"/>
        </div>
        <div class="absolute -z-10 top-0 right-0 w-96 h-96 bg-[#39FF14]/20 rounded-full blur-3xl"></div>
        <!-- Adicione o GIF aqui -->
        <!-- <img src="@/assets/hero-animation.gif" alt="Hero Animation" class="" />-->
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue'
import { Github, Linkedin, Mail } from 'lucide-vue-next'
import profileImageSrc from '@/assets/profile.jpg'

export default {
  name: 'HeroSection',
  components: {
    Github,
    Linkedin,
    Mail
  },
  setup() {
    const name = ref('Vitor Mariano')
    const role = ref('Ao longo do tempo, tenho me concentrado especialmente no uso do framework Laravel, encontrando nele um parceiro poderoso para criar aplicações web eficientes e de alto desempenho.')
    const profileImage = ref(profileImageSrc)
    const socials = [
      { name: 'Github', icon: Github, url: 'https://github.com/username' },
      { name: 'LinkedIn', icon: Linkedin, url: 'https://linkedin.com/in/username' },
      { name: 'Email', icon: Mail, url: 'mailto:email@exemplo.com' }
    ]

    return {
      name,
      role,
      profileImage,
      socials
    }
  }
}
</script>

<style scoped>
/* Você pode adicionar estilos personalizados para o GIF aqui */
</style>
