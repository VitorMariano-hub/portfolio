<template>
  <section
    class="min-h-screen flex items-center justify-center pt-28 md:pt-16 xl:pt-16"
  >
    <div class="container mx-auto px-4 grid md:grid-cols-2 gap-8 items-center">
      <div>
        <h2 class="text-5xl font-bold mb-4">
          Olá! Meu nome é
          <span class="text-[#39FF14]">{{ name }}</span
          >, desenvolvedor web full-stack<span class="text-[#39FF14]">.</span>
        </h2>
        <p class="text-xl mb-6">{{ role }}</p>
        <div class="flex gap-2 md:gap-4 lg:gap-4">
          <a
            href="#contact"
            class="bg-[#39FF14] text-black px-6 py-2 rounded hover:bg-[#00FFFF] transition-colors"
          >
            Contato
          </a>
          <a
            href="#projects"
            class="border border-[#39FF14] px-6 py-2 rounded hover:bg-[#39FF14] hover:text-black transition-colors"
          >
            Projetos
          </a>
          <download-pdf-button :pdf-url="pdfUrl" :pdf-file-name="pdfFileName" />
        </div>
        <div class="flex gap-4 mt-8">
          <a
            v-for="social in socials"
            :key="social.name"
            :href="social.url"
            target="_blank"
            class="hover:text-[#39FF14]"
          >
            <component :is="social.icon" class="w-6 h-6" />
          </a>
        </div>
      </div>
      <div class="relative mb-4">
        <div
          class="bg-[#2C2C2C] w-64 h-64 rounded-full mx-auto relative overflow-hidden border-4 border-[#ffffff]"
        >
          <img
            :src="profileImage"
            alt="Profile"
            class="w-full h-full object-cover"
          />
        </div>
        <div
          class="absolute -z-10 top-0 right-0 w-96 h-96 bg-[#39FF14]/20 rounded-full blur-3xl"
        ></div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
import { Github, Linkedin, Mail } from "lucide-vue-next";
import profileImageSrc from "@/assets/profile.jpg";
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
      "Graduando em Análise e Desenvolvimento de Sistemas, desenvolvedor web full-stack com mais de 3 anos de experiência. Entusiasta de tecnologia e apaixonado por programação."
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
};
</script>

<style scoped></style>
