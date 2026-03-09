<template>
  <section
    ref="hero"
    id="hero"
    class="min-h-screen flex items-center justify-center pt-28 md:pt-16 xl:pt-16 relative overflow-hidden"
    data-aos="fade-up"
    data-aos-duration="1000"
  >
    <!-- Background Glow Effect -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[500px] h-[500px] bg-[#39FF14]/10 rounded-full blur-[120px] -z-10"></div>

    <div class="container mx-auto px-4 grid md:grid-cols-2 gap-12 items-center relative z-10">
      <div>
        <p class="text-gray-400 text-lg mb-2 font-medium tracking-wide">
          Olá! Meu nome é
        </p>
        <h2 class="text-5xl md:text-7xl font-bold mb-6 leading-tight">
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-[#39FF14] to-[#00FFFF] drop-shadow-[0_0_10px_rgba(57,255,20,0.3)]">
            {{ name }}
          </span>
        </h2>
          
        <h3 class="text-2xl md:text-3xl text-gray-200 font-semibold mb-6">
          Desenvolvedor Full-Stack <span class="text-[#39FF14]">.</span>
        </h3>

        <p class="text-gray-400 text-lg mb-8 leading-relaxed max-w-lg">
          {{ role }}
        </p>

        <div class="flex flex-wrap gap-4">
          <a
            :href="whatsappLink"
            target="_blank"
            class="bg-[#39FF14] text-black font-bold px-8 py-3 rounded-md hover:bg-[#32e012] transition-all duration-300 transform hover:-translate-y-1 hover:shadow-[0_0_20px_rgba(57,255,20,0.4)]"
          >
            Entrar em Contato
          </a>
          <a
            href="#projects"
            class="border border-[#39FF14]/50 text-[#39FF14] px-8 py-3 rounded-md hover:bg-[#39FF14]/10 transition-all duration-300 transform hover:-translate-y-1"
          >
            Ver Projetos
          </a>
          <download-pdf-button :pdf-url="pdfUrl" :pdf-file-name="pdfFileName" />
        </div>
        
        <div class="flex gap-6 mt-10">
          <a
            v-for="social in socials"
            :key="social.name"
            :href="social.url"
            target="_blank"
            class="text-gray-400 hover:text-[#39FF14] transition-all duration-300 transform hover:scale-110"
          >
            <component :is="social.icon" class="w-6 h-6" />
          </a>
        </div>
      </div>

      <div class="relative flex justify-center md:justify-center" data-aos="fade-left" data-aos-delay="200">
        <div class="relative w-72 h-72 md:w-96 md:h-96">
          <!-- Decorative circle behind image -->
           <div class="absolute inset-0 bg-gradient-to-tr from-[#39FF14] to-[#00FFFF] rounded-full blur-2xl opacity-20 animate-pulse"></div>
           
          <div
            class="w-full h-full rounded-full border-2 border-[#39FF14]/30 relative overflow-hidden bg-[#0A0A0A] p-2"
          >
            <img
              :src="profileImage"
              alt="Profile"
              class="w-full h-full object-cover object-center rounded-full transition-all duration-500 hover:scale-105"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import { Github, Linkedin, Mail } from "lucide-vue-next";
import profileImageSrc from "@/assets/_profile.jpeg";
import DownloadPdfButton from "@/components/DownloadPdfButton.vue";

export default {
  name: "HeroSection",
  components: {
    Github,
    Linkedin,
    Mail,
    DownloadPdfButton
  },
  setup() {
    const name = ref("Vitor Mariano");
    const role = ref(
      "Graduado em Análise e Desenvolvimento de Sistemas, desenvolvedor web full-stack com mais de 5 anos de experiência. Entusiasta de tecnologia e apaixonado por programação."
    );
    const profileImage = ref(profileImageSrc);
    const socials = [
      {
        name: "Github",
        icon: Github,
        url: "https://github.com/VitorMariano-hub",
      },
      {
        name: "LinkedIn",
        icon: Linkedin,
        url: "https://www.linkedin.com/in/vitor-mariano-037b56138/",
      },
      { name: "Email", icon: Mail, url: "vitorma1992@gmail.com" },
    ];

    return {
      name,
      role,
      profileImage,
      socials,
      pdfUrl: "https://github.com/VitorMariano-hub/Curriculo/raw/main/VitorDesenvolvedorPHP.pdf",
      pdfFileName: "Vitor - Desenvolvedor Full-Stack PHP.pdf",
    };
  },
  computed: {
    whatsappLink() {
      const phone = '5513981977083';
      const message = encodeURIComponent('Olá! Gostaria de saber mais sobre seus projetos.');
      return `https://wa.me/${phone}?text=${message}`;
    }
  }
};
</script>
