<template>
  <DefaultLayout>
    <HeroSection />
    <ProjectsSection :projects="projects" />
    <AboutSectionVue />
    <JobsSection :jobs="jobs" />
    <XpSection />
  </DefaultLayout>
</template>

<script>
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import HeroSection from '@/components/home/HeroSection.vue'
import AboutSectionVue from '@/components/home/AboutSection.vue'
import ProjectsSection from '@/components/home/ProjectsSection.vue'
import ContactSection from '@/components/home/ContactSection.vue'
import XpSection from '@/components/home/XpSection.vue'
import JobsSection from '@/components/home/JobsSection.vue'


export default {
  name: 'HomeView',
  components: {
    DefaultLayout,
    HeroSection,
    AboutSectionVue,
    ProjectsSection,
    XpSection,
    ContactSection,
    JobsSection
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
        credentials: 'Usuário teste: userteste@teste.com | teste@123'
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
        title: 'Task Manager Api',
        description: 'A Task Manager API é uma API RESTful desenvolvida com Laravel e protegida por Laravel Sanctum para autenticação de usuários. Ela serve como backend para a aplicação de gerenciamento de tarefas Task Manager Web.',
        image: 'https://i.imgur.com/LY4XcNS.png',
        demo: 'https://task-manager-0wdh.onrender.com/api/documentation',
        github: 'https://github.com/VitorMariano-hub/task-manager',
        credentials: 'Usuário teste: userteste@teste.com | teste@123'
      },
      {
        id: 4,
        title: 'Princípios SOLID da Programação Orientada a Objetos.',
        description: 'Projeto desenvolvido com exemplos práticos dos 5 princípios do SOLID aplicados em PHP, focando em boas práticas de design, código limpo e testes automatizados.',
        image: 'https://images.ctfassets.net/bp521nfj3cq3/4pw3f1nT851svWyID3Bl46/58e6053ac0258636eef45f899c542706/Solid.png',
        github: 'https://github.com/VitorMariano-hub/solid-principles-php'
      },
      {
        id: 5,
        title: 'Wildbeast',
        description: 'O projeto "Wildbeast" é um site com uma única página, focado na apresentação de um conceito visual impactante e responsivo.',
        image: 'https://camo.githubusercontent.com/ac288fce0e7b73dc8f2c93912f63c046923c6524d773e88f72319c1f849b7fe3/68747470733a2f2f75706c6f61646465696d6167656e732e636f6d2e62722f696d616765732f3030332f3338392f3831342f6f726967696e616c2f6c622e504e473f31363239343033353833',
        demo: 'https://vitormariano-hub.github.io/Wildbeast',
        github: 'https://github.com/VitorMariano-hub/Wildbeast'
      },
    ]

    const jobs = [
       {
        id: 1,
        title: 'Loja Virtual - Vanilla Store',
        description: 'Configuração e personalização completa da loja virtual na plataforma Nuvemshop, incluindo registro de domínio, integração com sistemas de pagamento e frete, ajustes de design, otimizações de SEO e performance, além de melhorias na experiência do usuário. Suporte nas configurações da loja para uma operação eficiente e segura.',
        link: 'https://www.storevanilla.com.br/',
        image: 'https://i.imgur.com/SS5O1QA.png',
      },
      {
        id: 2,
        title: 'Site Institucional - WM Express',
        description: 'Projeto completo realizado de ponta a ponta: desenvolvimento do site responsivo, registro de domínio, configuração de hospedagem, deploy, SEO on-page, integração com Google Meu Negócio e suporte inicial em campanhas Google Ads. Foco total em performance, usabilidade e presença digital.',
        link: 'https://wmexpress.com.br/',
        image: 'https://i.imgur.com/8IyoXUB.png',
      }
    ];

    return {
      projects,
      jobs
    }
  }
}
</script>
