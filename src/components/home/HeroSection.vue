<template>
  <section
    ref="hero"
    id="hero"
    class="min-h-screen flex items-center justify-center pt-28 md:pt-16 xl:pt-16 relative overflow-hidden"
    data-aos="fade-up"
    data-aos-duration="1000"
  >
    <!-- Background Aurora Glow Effects -->
    <div class="absolute top-[10%] left-[5%] w-[300px] md:w-[600px] h-[300px] md:h-[600px] bg-[#39FF14]/8 rounded-full blur-[100px] md:blur-[150px] -z-10 animate-aurora-1"></div>
    <div class="absolute bottom-[10%] right-[5%] w-[300px] md:w-[600px] h-[300px] md:h-[600px] bg-[#00FFFF]/8 rounded-full blur-[100px] md:blur-[150px] -z-10 animate-aurora-2"></div>

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

      <div class="relative flex justify-center md:justify-center group" data-aos="fade-left" data-aos-delay="200">
        <div class="relative w-72 h-72 md:w-96 md:h-96">
          <!-- Decorative blurred gradient background with enhanced scale and opacity on hover -->
          <div class="absolute inset-0 bg-gradient-to-tr from-[#39FF14] to-[#00FFFF] rounded-[2rem] md:rounded-[3rem] blur-3xl opacity-20 group-hover:opacity-40 group-hover:scale-105 transition-all duration-500"></div>
          
          <!-- Outer border frame with rotation effect -->
          <div class="absolute inset-0 border border-[#39FF14]/30 rounded-[2rem] md:rounded-[3rem] transform rotate-3 group-hover:rotate-0 transition-transform duration-500 -z-10"></div>
          <div class="absolute inset-0 border border-[#00FFFF]/20 rounded-[2rem] md:rounded-[3rem] transform -rotate-3 group-hover:rotate-0 transition-transform duration-500 -z-10"></div>

          <!-- Main Image Container with asymmetric rounded corners -->
          <div class="w-full h-full rounded-[2rem] md:rounded-[3rem] border-2 border-gradient overflow-hidden bg-[#0A0A0A] p-2 relative z-10 transition-all duration-500 group-hover:scale-[1.02]">
            <img
              :src="profileImage"
              alt="Profile"
              class="w-full h-full object-cover object-center rounded-[1.6rem] md:rounded-[2.6rem] transition-all duration-500"
            />
          </div>

          <!-- Floating Badges (Dynamic tech tags) -->
          <div class="absolute -top-4 -left-4 bg-[#0A0A0A]/80 backdrop-blur-md border border-[#39FF14]/30 text-[#39FF14] px-4 py-2 rounded-full text-xs font-semibold flex items-center gap-1.5 shadow-lg z-20 animate-float-slow">
            <span class="w-2 h-2 rounded-full bg-[#39FF14] animate-ping"></span>
            Laravel 12
          </div>

          <div class="absolute top-1/2 -right-8 bg-[#0A0A0A]/80 backdrop-blur-md border border-[#00FFFF]/30 text-[#00FFFF] px-4 py-2 rounded-full text-xs font-semibold flex items-center gap-1.5 shadow-lg z-20 animate-float-medium">
            <span class="w-2 h-2 rounded-full bg-[#00FFFF] animate-ping"></span>
            Vue.js 3
          </div>

          <div class="absolute -bottom-4 left-6 bg-[#0A0A0A]/80 backdrop-blur-md border border-gray-700 text-gray-300 px-4 py-2 rounded-full text-xs font-semibold flex items-center gap-1.5 shadow-lg z-20 animate-float-fast">
            <span class="w-2 h-2 rounded-full bg-[#39FF14]"></span>
            SQL & APIs
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
      "Desenvolvedor Full-Stack especializado em arquitetura de alto desempenho com Laravel (PHP) e interfaces dinâmicas com Vue.js. Focado em APIs RESTful escaláveis, testes automatizados e código limpo."
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
      pdfUrl: "https://github.com/VitorMariano-hub/Curriculo/raw/main/Vitor_Mariano_Dev_CV.pdf",
      pdfFileName: "Vitor_Mariano-Desenvolvedor.pdf",
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

<style scoped>
.border-gradient {
  border-image: linear-gradient(to right, #39FF14, #00FFFF) 1;
}

@keyframes aurora1 {
  0%, 100% { transform: translate(0px, 0px) scale(1); }
  50% { transform: translate(40px, -60px) scale(1.15); }
}

@keyframes aurora2 {
  0%, 100% { transform: translate(0px, 0px) scale(1); }
  50% { transform: translate(-40px, 60px) scale(1.15); }
}

@keyframes floatSlow {
  0%, 100% { transform: translateY(0px) rotate(-1deg); }
  50% { transform: translateY(-10px) rotate(1deg); }
}

@keyframes floatMedium {
  0%, 100% { transform: translateY(0px) rotate(1deg); }
  50% { transform: translateY(-8px) rotate(-1deg); }
}

@keyframes floatFast {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-6px); }
}

.animate-aurora-1 {
  animation: aurora1 25s ease-in-out infinite;
}

.animate-aurora-2 {
  animation: aurora2 30s ease-in-out infinite;
}

.animate-float-slow {
  animation: floatSlow 6s ease-in-out infinite;
}

.animate-float-medium {
  animation: floatMedium 5s ease-in-out infinite;
}

.animate-float-fast {
  animation: floatFast 4s ease-in-out infinite;
}
</style>
