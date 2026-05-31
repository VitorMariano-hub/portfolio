<template>
  <DefaultLayout>
    <HeroSection />
    <ProjectsSection :projects="projects" />
    <XpSection />
    <AboutSectionVue />
    <JobsSection :jobs="jobs" />
  </DefaultLayout>
</template>

<script>
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import HeroSection from '@/components/home/HeroSection.vue'
import XpSection from '@/components/home/XpSection.vue'
import ProjectsSection from '@/components/home/ProjectsSection.vue'
import AboutSectionVue from '@/components/home/AboutSection.vue'
import JobsSection from '@/components/home/JobsSection.vue'
import ContactSection from '@/components/home/ContactSection.vue'


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
        id: 7,
        title: 'MetaVaga - Gerenciador de Estudos',
        description: 'Plataforma gamificada inteligente para concurseiros organizarem seus ciclos de estudo e edital. Desenvolvido com Laravel 12, Tailwind CSS v4 e Alpine.js, conta com métricas de desempenho em questões, conquistas, histórico de progresso e modo escuro nativo.',
        image: '/metavaga.png',
        demo: 'https://concurso-tracker.vitormariano.dev.br/',
        github: 'https://github.com/VitorMariano-hub/concurso-tracker'
      },
      {
        id: 1,
        title: 'Task Manager Web',
        description: 'Aplicação de gerenciamento de tarefas em estilo Kanban, com frontend em Vue.js e backend Laravel. Permite criar, mover e excluir tarefas entre colunas com drag & drop.',
        image: 'https://i.postimg.cc/9XqJXKZR/Capturar.png',
        demo: 'https://task-manager-web.vitormariano.dev.br/login',
        github: 'https://github.com/VitorMariano-hub/task-manager-web',
        credentials: 'Usuário teste: user.teste@gmail.com | Senha@123'
      },
      {
        id: 2,
        title: 'Sistema de Enquetes',
        description: 'Aplicação web desenvolvida com Laravel. Administradores autenticados podem criar e excluir enquetes, enquanto o público tem acesso a elas e pode votar apenas uma vez por enquete, com verificação feita por IP.',
        image: 'https://i.imgur.com/vMwCala.png',
        demo: 'https://polls.vitormariano.dev.br/',
        github: 'https://github.com/VitorMariano-hub/polls-system-web',
        credentials: 'Usuário teste: admin@teste.com | Senha@123'
      },
      {
        id: 3,
        title: 'Task Manager Api',
        description: 'A Task Manager API é uma API RESTful desenvolvida com Laravel e protegida por Laravel Sanctum para autenticação de usuários. Ela serve como backend para a aplicação de gerenciamento de tarefas Task Manager Web.',
        image: 'https://i.imgur.com/LY4XcNS.png',
        demo: 'https://task-manager.vitormariano.dev.br/api/documentation',
        github: 'https://github.com/VitorMariano-hub/task-manager',
        credentials: 'Usuário teste: user.teste@gmail.com | Senha@123'
      },
      {
        id: 5,
        title: 'Serviço de OCR e Extração de Dados de Comprovantes com IA.',
        description: 'Este é um projeto de estudo, desenvolvido com Laravel, que permite processar comprovantes bancários enviados em imagens ou PDFs, extraindo dados estruturados através de OCR e interpretação de texto com inteligência artificial.',
        image: 'https://i.imgur.com/v0YeSiH.png',
        github: 'https://github.com/VitorMariano-hub/ia-receipt'
      },
      {
        id: 6,
        title: 'Wildbeast',
        description: 'O projeto "Wildbeast" é um site com uma única página, focado na apresentação de um conceito visual impactante e responsivo.',
        image: 'https://i.imgur.com/JMJ01en.png',
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
