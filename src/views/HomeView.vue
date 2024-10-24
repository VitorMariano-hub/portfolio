<template>
  <DefaultLayout>
    <HeroSection />
    <AboutSectionVue />
    <ProjectsSection :projects="projects" />
    <XpSection />
    <ContactSection />
  </DefaultLayout>
</template>

<script>
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import HeroSection from '@/components/home/HeroSection.vue'
import AboutSectionVue from '@/components/home/AboutSection.vue'
import ProjectsSection from '@/components/home/ProjectsSection.vue'
import ContactSection from '@/components/home/ContactSection.vue'
import XpSection from '@/components/home/XpSection.vue'


export default {
  name: 'HomeView',
  components: {
    DefaultLayout,
    HeroSection,
    AboutSectionVue,
    ProjectsSection,
    XpSection,
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
        image: 'https://camo.githubusercontent.com/37c9949956b9d557437e4837f6e97b81b32d3355106b55eadee158158a66dc5d/68747470733a2f2f75706c6f61646465696d6167656e732e636f6d2e62722f696d616765732f3030332f3339322f3835352f6f726967696e616c2f676f726a6574612e504e473f31363239353832383736',
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
    return {
      projects
    }
  }
}
</script>
