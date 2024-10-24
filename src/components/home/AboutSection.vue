<template>
  <section id="about" class="py-20 bg-[#2C2C2C]">
    <div class="container mx-auto px-4">
      <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Sobre Mim</h3>
      <div class="grid md:grid-cols-2 gap-8">
        <div class="space-y-4 text-lg">
          <p>Desenvolvedor web full-stack com mais de três anos de experiência. Ao longo da minha trajetória profissional, tive a oportunidade de atuar como desenvolvedor full stack em projetos nos setores financeiro e de ensino online.</p>
          <p>Minha principal área de atuação é o desenvolvimento backend, onde utilizo PHP e Laravel para integrar bancos de dados relacionais e criar APIs RESTful.</p>
          <p>Possuo conhecimentos e experiência em frontend também, com foco no desenvolvimento de interfaces dinâmicas e responsivas utilizando tecnologias como JavaScript, Vue.js, jQuery, CSS3, Tailwind, Bootstrap, HTML5.</p>
        </div>
        
        <div class="grid grid-cols-2 gap-4">
          <div v-for="skill in skills" :key="skill.title" class="bg-[#0A0A0A] p-4 rounded">
            <div class="flex gap-2">
              <h4 class="font-bold mb-2">{{ skill.title }} </h4>
              <component :is="skill.icon" class="w-6 h-6 text-[#39FF14] mb-2" />
            </div>
            <p class="text-sm mb-2">{{ skill.description }}</p>
            <ul>
              <li v-for="technology in skill.technologies" :key="technology" class="text-sm">
                <span class="text-[#39FF14] font-bold text-xl">-</span> {{ technology }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import { Terminal, Code } from 'lucide-vue-next';

export default {
  name: 'AboutSection',
  setup() {
    const skills = [
      {
        title: 'Backend',
        icon: Terminal, 
        description: 'Desenvolvimento de APIs RESTful',
        technologies: ['PHP', 'Laravel', 'SQL', 'MySQL']
      },
      {
        title: 'Frontend',
        icon: Code,
        description: 'Desenvolvimento de interfaces',
        technologies: ['JavaScript', 'Vue.js', 'jQuery', 'CSS3', 'Tailwind', 'Bootstrap', 'HTML5']
        
      }
    ]
    return {
      skills
    }
  }
}
</script>

<style>

</style>