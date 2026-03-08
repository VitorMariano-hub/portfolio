<template>
  <section ref="experience" id="experience" class="py-20 bg-[#0A0A0A] relative overflow-hidden">
    <!-- Background element for visual interest -->
    <div class="absolute top-0 right-0 w-96 h-96 bg-[#00FFFF] opacity-5 rounded-full blur-3xl -translate-y-1/2 translate-x-1/2"></div>
    <div class="absolute bottom-0 left-0 w-64 h-64 bg-[#39FF14] opacity-5 rounded-full blur-3xl translate-y-1/2 -translate-x-1/2"></div>

    <div class="container mx-auto px-4 relative z-10">
      <h3 class="text-3xl md:text-4xl font-bold mb-16 text-[#00FFFF] text-center uppercase tracking-widest relative inline-block left-1/2 -translate-x-1/2">
        Experiência Profissional
        <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#00FFFF] to-[#39FF14]"></span>
      </h3>
      
      <div class="relative">
        <!-- Vertical Timeline Line -->
        <div class="absolute left-4 md:left-1/2 h-full w-0.5 bg-gradient-to-b from-[#00FFFF] via-[#39FF14] to-[#0A0A0A] hidden md:block transform -translate-x-1/2"></div>
        
        <div class="space-y-12">
          <div 
            v-for="(experience, index) in experiences" 
            :key="experience.company" 
            class="relative flex flex-col md:flex-row items-start group"
            :class="index % 2 === 0 ? 'md:flex-row-reverse' : ''"
            data-aos="fade-up"
          >
            <!-- Timeline Dot -->
            <div class="absolute left-4 md:left-1/2 w-4 h-4 bg-[#0A0A0A] border-2 border-[#00FFFF] rounded-full z-10 transform -translate-x-1/2 mt-6 group-hover:bg-[#39FF14] group-hover:border-[#39FF14] transition-colors duration-300 hidden md:block shadow-[0_0_10px_rgba(0,255,255,0.5)]"></div>

            <!-- Content -->
            <div class="w-full md:w-1/2 pl-12 md:pl-0" :class="index % 2 === 0 ? 'md:pr-12 text-left md:text-right' : 'md:pl-12 text-left'">
              <div class="bg-[#2C2C2C]/50 backdrop-blur-sm p-6 rounded-xl border border-[#333] hover:border-[#00FFFF]/30 transition-all duration-300 hover:shadow-[0_0_20px_rgba(0,255,255,0.1)] group-hover:-translate-y-1">
                
                <div class="flex flex-col mb-4" :class="index % 2 === 0 ? 'md:items-end' : 'md:items-start'">
                  <h4 class="text-2xl font-bold text-[#39FF14] mb-1">{{ experience.company }}</h4>
                  <p class="text-lg text-white font-medium">{{ experience.position }}</p>
                  <span class="inline-block px-3 py-1 mt-2 text-xs font-bold text-[#0A0A0A] bg-[#00FFFF] rounded-full">
                    {{ experience.period }}
                  </span>
                </div>

                <p class="mb-4 text-gray-300 leading-relaxed text-sm">
                   <ul class="space-y-2">
                    <li v-for="(task, tIndex) in experience.tasks" :key="tIndex" class="flex items-start" :class="index % 2 === 0 ? 'md:flex-row-reverse md:text-right' : ''">
                      <span class="text-[#00FFFF] mr-2 mt-1" :class="index % 2 === 0 ? 'md:mr-0 md:ml-2' : ''">▹</span>
                      <span>{{ task }}</span>
                    </li>
                  </ul>
                </p>

                <!-- Tech Stack Badges -->
                <div class="flex flex-wrap gap-2 mt-4" :class="index % 2 === 0 ? 'md:justify-end' : 'md:justify-start'">
                  <span 
                    v-for="tech in experience.techStack" 
                    :key="tech"
                    class="px-2 py-1 text-xs font-mono text-[#00FFFF] border border-[#00FFFF]/30 rounded bg-[#00FFFF]/5 hover:bg-[#00FFFF]/10 transition-colors"
                  >
                    {{ tech }}
                  </span>
                </div>
              </div>
            </div>
          </div>
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
        company: 'K.education',
        position: 'Desenvolvedor PHP',
        period: 'Jan 2024 - Atualmente',
        tasks: [
          'Desenvolvimento e manutenção do backend em Laravel para plataforma de gestão acadêmica (CMS).',
          'Criação de APIs RESTful integradas a aplicações web e mobile.',
          'Implementação de dashboards administrativos com dados em tempo real.',
          'Criação de sistema de conversação para registro de aulas, presenças e avaliações.',
          'Desenvolvimento de módulo de RH voltado à organização de processos e informações internas.',
          'Atuação contínua com foco em performance, estabilidade e usabilidade do sistema.'
        ],
        techStack: ['PHP', 'Laravel', 'API REST', 'CMS', 'Real-time']
      },
      {
        company: 'Cartão Pagcorp',
        position: 'Desenvolvedor PHP',
        period: 'Jul 2022 - Jan 2024',
        tasks: [
          'Atuação no desenvolvimento e sustentação da plataforma “Acesso do Gestor”, sistema corporativo de controle de despesas.',
          'Desenvolvimento de funcionalidades em Laravel (PHP) utilizando SQL Server como banco de dados.',
          'Implementação de sistema de ativação contactless com filtros e ações em lote.',
          'Integração com APIs de faturas e extratos, permitindo visualização em tempo real.',
          'Otimização de performance no processamento de extratos e comprovantes (server-side + Redis).',
          'Migração de sistemas legados de Scriptcase para Laravel.'
        ],
        techStack: ['PHP', 'Laravel', 'SQL Server', 'Redis', 'API Integration']
      },
      {
        company: 'Corretora N&G',
        position: 'Analista de suporte de sistemas',
        period: 'Mai 2019 - Jun 2022',
        tasks: [
          'Desenvolvimento da Área do Cliente e de sistemas de atendimento (Laravel/MySQL).',
          'Manutenção e evolução do sistema de vendas de seguros (MetLife) em PHP OO.',
          'Desenvolvimento e melhorias contínuas na intranet corporativa (WordPress).',
          'Integração com o chatbot TakeBlip para atendimento automatizado.',
          'Correções e melhorias em sistemas legados em PHP.'
        ],
        techStack: ['PHP', 'Laravel', 'MySQL', 'Bootstrap', 'JavaScript', 'WordPress', 'Git']
      },
      {
        company: 'TOC Terminais de Carga',
        position: 'Técnico de suporte em TI',
        period: 'Out 2016 - Mai 2019',
        tasks: [
          'Suporte ao parque tecnológico e aos usuários internos.',
          'Administração de servidores físicos e virtuais.',
          'Gestão de backups.',
          'Ambientes Windows Server, Active Directory e VMs.'
        ],
        techStack: ['Windows Server', 'Linux', 'Active Directory', 'Virtualization']
      }
    ]
    return {
      experiences
    }
  }
}
</script>

<style scoped>
/* Optional: Add custom scrollbar for the timeline container if needed */
</style>