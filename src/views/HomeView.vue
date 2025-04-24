<template>
  <DefaultLayout>
    <HeroSection />
    <ProjectsSection :projects="projects" />
    <AboutSectionVue />
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
        title: 'Task Manager Web',
        description: 'Aplicação de gerenciamento de tarefas em estilo Kanban, com frontend em Vue.js e backend Laravel. Permite criar, mover e excluir tarefas entre colunas com drag & drop.',
        image: 'https://i.postimg.cc/9XqJXKZR/Capturar.png',
        demo: 'https://task-manager-web-pxgc.onrender.com/',
        github: 'https://github.com/VitorMariano-hub/task-manager-web',
        credentials: 'Usuário teste: teste@teste.com | teste@123'
      },
      {
        id: 2,
        title: 'Sistema de Enquetes',
        description: 'Aplicação web desenvolvida com Laravel. Administradores autenticados podem criar e excluir enquetes, enquanto o público tem acesso a elas e pode votar apenas uma vez por enquete, com verificação feita por IP.',
        image: 'https://i.imgur.com/vMwCala.png',
        demo: 'https://polls-system-web-production.up.railway.app',
        github: 'https://github.com/VitorMariano-hub/polls-system-web',
        credentials: 'Usuário teste: admin@example.com | password@123'
      },
      {
        id: 3,
        title: 'Wildbeast',
        description: 'O projeto "Wildbeast" é um site com uma única página, focado na apresentação de um conceito visual impactante e responsivo.',
        image: 'https://camo.githubusercontent.com/ac288fce0e7b73dc8f2c93912f63c046923c6524d773e88f72319c1f849b7fe3/68747470733a2f2f75706c6f61646465696d6167656e732e636f6d2e62722f696d616765732f3030332f3338392f3831342f6f726967696e616c2f6c622e504e473f31363239343033353833',
        demo: 'https://vitormariano-hub.github.io/Wildbeast',
        github: 'https://github.com/VitorMariano-hub/Wildbeast'
      },
    ]
    return {
      projects
    }
  }
}
</script>
