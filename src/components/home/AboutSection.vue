<template>
  <section ref="about" id="about" class="py-20 bg-[#0A0A0A] relative overflow-hidden">
     <!-- Background Glow -->
    <div class="absolute top-1/2 left-0 w-64 h-64 bg-[#00FFFF] opacity-5 rounded-full blur-3xl -translate-y-1/2 -translate-x-1/2"></div>

    <div class="container mx-auto px-4 relative z-10">
      <h3 class="text-3xl md:text-4xl font-bold mb-16 text-[#00FFFF] text-center uppercase tracking-widest relative inline-block left-1/2 -translate-x-1/2">
        Sobre Mim
        <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#00FFFF] to-[#39FF14]"></span>
      </h3>
      
      <div class="grid md:grid-cols-2 gap-12 items-start">
        <div class="space-y-6 text-lg text-gray-300 leading-relaxed font-light">
          <p class="border-l-2 border-[#39FF14] pl-4">
            Desenvolvedor web full-stack com mais de 5 anos de experiência. Ao longo da minha trajetória profissional, tive a oportunidade de atuar como desenvolvedor full stack em projetos nos setores financeiro e de ensino online.
          </p>
          <p>
            Minha principal área de atuação é o desenvolvimento backend, onde utilizo <strong class="text-white">PHP</strong> e <strong class="text-white">Laravel</strong> para integrar bancos de dados relacionais e criar APIs RESTful robustas.
          </p>
          <p>
            Possuo conhecimentos e experiência em frontend também, com foco no desenvolvimento de interfaces dinâmicas e responsivas utilizando tecnologias modernoas como <strong class="text-white">Vue.js</strong> e <strong class="text-white">Tailwind CSS</strong>.
          </p>
        </div>
        
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
          <div 
            v-for="skill in skills" 
            :key="skill.title" 
            class="bg-[#2C2C2C]/30 backdrop-blur-sm border border-[#333] p-6 rounded-xl transition-all duration-300 hover:border-[#39FF14]/50 hover:shadow-[0_0_15px_rgba(57,255,20,0.1)] group"
          >
            <div class="flex items-center gap-3 mb-4">
              <div class="p-2 bg-[#39FF14]/10 rounded-lg group-hover:bg-[#39FF14]/20 transition-colors">
                <component :is="skill.icon" class="w-6 h-6 text-[#39FF14]" />
              </div>
              <h4 class="font-bold text-xl text-white">{{ skill.title }} </h4>
            </div>
            
            <p class="text-sm text-gray-400 mb-4 h-10">{{ skill.description }}</p>
            
            <ul class="space-y-2">
              <li v-for="technology in skill.technologies" :key="technology" class="text-sm flex items-center text-gray-300">
                <span class="w-1.5 h-1.5 bg-[#00FFFF] rounded-full mr-2"></span>
                {{ technology }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import { Terminal, Code, Database, Layout } from 'lucide-vue-next';

export default {
  name: 'AboutSection',
  setup() {
    const skills = [
      {
        title: 'Backend',
        icon: Terminal, 
        description: 'Arquitetura de sistemas robustos e escaláveis.',
        technologies: ['PHP 8+', 'Laravel', 'Node.js', 'API RESTful']
      },
      {
        title: 'Frontend',
        icon: Layout,
        description: 'Interfaces modernas e responsivas.',
        technologies: ['Vue.js 3', 'Tailwind CSS', 'JavaScript (ES6+)', 'HTML5/CSS3']
      },
       {
        title: 'Database',
        icon: Database,
        description: 'Modelagem e otimização de dados.',
        technologies: ['MySQL', 'PostgreSQL', 'Redis', 'SQL Server']
      },
       {
        title: 'Tools',
        icon: Code,
        description: 'Ferramentas de versionamento e deploy.',
        technologies: ['Git/GitHub', 'Docker', 'CI/CD', 'Linux']
      }
    ]
    return {
      skills
    }
  },
}
</script>

<style scoped>
</style>