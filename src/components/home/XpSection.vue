<template>
<section ref="experience" id="experience" class="py-20 bg-[#0A0A0A] ">
  <div class="container mx-auto px-4">
    <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Experiência Profissional</h3>
    <div class="space-y-8">
      <div 
        v-for="experience in experiences" 
        :key="experience.company" 
        class="bg-[#2C2C2C] p-6 rounded-md transition-transform duration-300"
        data-aos="fade-up"
      >
        <h4 class="text-xl font-bold text-[#39FF14]">{{ experience.company }}</h4>
        <p class="text-sm font-bold mb-2 text-[#E0E0E0]">{{ experience.position }} - {{ experience.period }}</p>
        <p class="mb-2 text-[#E0E0E0]">{{ experience.description }}</p>
        <ul class="list-disc pl-5 mt-2">
          <li v-for="(task, index) in experience.tasks" :key="index">{{ task }}</li>
        </ul>
      </div>
    </div>
  </div>
</section>
</template>

<script>
export default {
  name: 'XpSection',
  setup() {
    const experiences = [
      {
        company: 'Kenny Idiomas',
        position: 'Desenvolvedor Web Full-Stack',
        period: '2024 - Atualmente',
        description: 'Desenvolvimento de funcionalidades e integrações para o painel administrativo e sistema de ensino online, utilizando Laravel no backend e Vue.js, Tailwind e Bootstrap no frontend.',
        tasks: [
          'Desenvolvimento de funcionalidades e integrações com Laravel e Vue.js.',
          'Criação de painéis administrativos escolares e municipais.',
          'Desenvolvimento do sistema de conversação, incluindo aulas, notas e gestão de alunos/professores.',
          'Criação de dashboards interativos com dados administrativos.',
          'Manutenção e sustentação do sistema com foco em performance e estabilidade.'
        ]
      },
      {
        company: 'Cartão Pagcorp',
        position: 'Desenvolvedor PHP',
        period: '2022 - 2024',
        description: 'Atuei no desenvolvimento de sistemas administrativos em Laravel, com foco em performance, integrações com APIs e sustentação de aplicações.',
        tasks: [
          'Sistema de Ativação Contactless: Ações em lote com filtros dinâmicos.',
          'Faturas: Integração com APIs, visualização com tabelas dinâmicas e modais com status em tempo real.',
          'Campanhas de Premiação: Upload de CSV e imagens, relatórios gerados via API.',
          'Performance em Extratos e Comprovantes: Uso de paginação server-side e Redis.',
          'Migração de Sistemas Legados: De Scriptcase para Laravel.',
          'Sustentação de Sistemas: Correções, ajustes e evolução contínua.'
        ]
      },
      {
        company: 'Nunes & Grossi Benefícios',
        position: 'Analista de suporte de sistemas',
        period: '2019 - 2022',
        description: 'Atuei no desenvolvimento e sustentação de sistemas internos e voltados ao cliente, com foco em estabilidade, performance e integração com parceiros.',
        tasks: [
          'Área do Cliente: Funcionalidades em Laravel para gerenciamento de serviços.',
          'Sistema de Vendas de Seguros (MetLife): Manutenção e evolução do sistema comercial.',
          'Intranet Corporativa: Desenvolvimento e melhorias em processos internos.',
          'Chatbot TakeBlip: Integração e automação de atendimento ao cliente.',
          'Sistemas Legados: Correções e melhorias em PHP legado.'
        ]
      }
    ]
    return {
      experiences
    }
  }
}
</script>

<style>

</style>