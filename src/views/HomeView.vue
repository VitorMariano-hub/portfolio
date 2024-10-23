<template>
  <DefaultLayout>
    <HeroSection />
    <AboutSectionVue :about="about" />
    <ProjectsSection :projects="projects" />
    <ContactSection />
  </DefaultLayout>
</template>

<script>
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import HeroSection from '@/components/home/HeroSection.vue'
import AboutSectionVue from '@/components/home/AboutSection.vue'
import ProjectsSection from '@/components/home/ProjectsSection.vue'
import ContactSection from '@/components/home/ContactSection.vue'


export default {
  name: 'HomeView',
  components: {
    DefaultLayout,
    HeroSection,
    AboutSectionVue,
    ProjectsSection,
    ContactSection
  },
  setup() {
    const projects = [
      {
        id: 1,
        title: 'Wildbeast',
        description: 'O projeto "Wildbeast" é um site com uma única página, focado na apresentação de um conceito visual impactante e responsivo.',
        image: 'https://camo.githubusercontent.com/ac288fce0e7b73dc8f2c93912f63c046923c6524d773e88f72319c1f849b7fe3/68747470733a2f2f75706c6f61646465696d6167656e732e636f6d2e62722f696d616765732f3030332f3338392f3831342f6f726967696e616c2f6c622e504e473f31363239343033353833',
        demo: 'https://vitormariano-hub.github.io/Wildbeast',
        github: 'https://github.com/VitorMariano-hub/Wildbeast'
      },
      {
        id: 2,
        title: 'Listar CEP',
        description: 'Desenvolvido em html, css e javascript, o projeto tem a finalidade de utilizar uma API externa para listar os CEPs de uma cidade específica.',
        image: 'https://private-user-images.githubusercontent.com/69535241/379345410-d55d2426-1f6b-410a-814a-59325f84d27f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3Mjk3MjE3MDksIm5iZiI6MTcyOTcyMTQwOSwicGF0aCI6Ii82OTUzNTI0MS8zNzkzNDU0MTAtZDU1ZDI0MjYtMWY2Yi00MTBhLTgxNGEtNTkzMjVmODRkMjdmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDEwMjMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQxMDIzVDIyMTAwOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWQ3ODU0ZjJjZDllY2ExMjdkZWM4ZjYxZDYzMzU2N2U5YTQ0ZjgxOTk1ZjlhMmRmOTk3ODYzYTgwOTJjZDUwYzEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.NZqFyCYI0qgkTP3oPIKro2Lf-g1kCfudTybRTi7VXxg',
        demo: 'https://vitormariano-hub.github.io/jscep/',
        github: 'https://github.com/VitorMariano-hub/jscep'
      },
      {
        id: 3,
        title: 'Calculadora de gorjetas',
        description: 'Desenvolvido em html, css e javascript, o projeto tem a finalidade de mostrar as gorjetas de uma conta especifca de um cliente.',
        image: 'https://camo.githubusercontent.com/37c9949956b9d557437e4837f6e97b81b32d3355106b55eadee158158a66dc5d/68747470733a2f2f75706c6f61646465696d6167656e732e636f6d2e62722f696d616765732f3030332f3339322f3835352f6f726967696e616c2f676f726a6574612e504e473f31363239353832383736',
        demo: 'https://vitormariano-hub.github.io/APP-Gorjetas/',
        github: 'https://github.com/VitorMariano-hub/APP-Gorjetas'
      }
    ]
    const about = [
      'Desenvolvedor web full-stack com mais de três anos de experiência. Ao longo da minha trajetória profissional, tive a oportunidade de atuar como desenvolvedor full stack em projetos nos setores financeiro e de ensino online.',
      'Minha principal área de atuação é o desenvolvimento backend, onde utilizo PHP e Laravel para integrar bancos de dados relacionais e criar APIs RESTful.',
      'Possuo conhecimentos e experiência em frontend também, com foco no desenvolvimento de interfaces dinâmicas e responsivas utilizando tecnologias como JavaScript, Vue.js, jQuery, CSS3, Tailwind, Bootstrap, HTML5.',
    ]




    return {
      projects,
      about
    }
  }
}
</script>
