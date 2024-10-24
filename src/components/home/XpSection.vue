<template>
<section id="experience" class="py-20 bg-[#0A0A0A] border-t border-[#292929]">
  <div class="container mx-auto px-4">
    <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Experiência Profissional</h3>
    <div class="space-y-8">
      <div 
        v-for="experience in experiences" 
        :key="experience.company" 
        class="bg-[#2C2C2C] p-6 rounded-lg border border-[#C0C0C0]/20"
      >
        <h4 class="text-xl font-bold text-[#39FF14]">{{ experience.company }}</h4>
        <p class="text-sm font-bold mb-2 text-[#E0E0E0]">{{ experience.position }} - {{ experience.period }}</p>
        <p>{{ experience.description }}</p>
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
        description: 'Atuo no desenvolvimento de novas funcionalidades e integrações no painel administrativo e sistema de ensino online, utilizando Laravel no backend e Vue.js, jQuery, Tailwind e Bootstrap no frontend. Minha atuação é Full Stack, abrangendo desde a implementação de models, controllers, regras de negócios e consultas SQL utilizando o Eloquent ORM no Laravel, até a criação de componentes dinâmicos e interativos com Vue.js e jQuery, além de interfaces responsivas com Tailwind e Bootstrap.',
      },
      {
        company: 'Cartão Pagcorp',
        position: 'Desenvolvedor PHP',
        period: '2022 - 2024',
        description: 'Fui responsável em aplicar manutenção preventiva/corretiva e desenvolver novas funcionalidades nos sistemas, utilizando a arquitetura MVC e os recursos oferecidos pelo Laravel, como Eloquent ORM e Blade Templates. Além disso, trabalhei com as tecnologias de front-end: HTML5, CSS3, jQuery e Bootstrap, para criação de interfaces de usuário intuitivas e responsivas, melhorando a experiência do usuário final.',
      },
    ]
    return {
      experiences
    }
  }
}
</script>

<style>

</style>