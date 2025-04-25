<template>
  <section ref="projects" id="projects" class="py-20">
    <div class="container mx-auto px-4">
      <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Projetos</h3>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="project in visibleProjects" 
          :key="project.id" 
          class="bg-[#2C2C2C] rounded-md overflow-hidden group transition-transform duration-300 hover:scale-[1.02]"
          data-aos="fade-up"
        >
          <div class="aspect-video bg-[#0A0A0A]">
            <img 
              :src="project.image" 
              :alt="project.title" 
              class="w-full h-full object-cover transition duration-300 group-hover:opacity-80"
            />
          </div>
          <div class="p-4">
            <h4 class="text-xl font-bold mb-2">{{ project.title }}</h4>
            <p class="text-sm mb-4 ">{{ project.description }}</p>
            <p class="text-sm mb-2">{{ project.credentials }}</p>
            <div class="flex gap-2">
              <a 
                v-if="project.demo" 
                :href="project.demo" 
                class="text-sm text-[#39FF14] hover:text-[#00FFFF] flex items-center gap-1 transition duration-300"
                target="_blank"
              >
                Demo 
                <external-link-icon class="w-4 h-4 transform group-hover:translate-x-1 transition duration-300"/>
              </a>
              <a 
                v-if="project.github" 
                :href="project.github" 
                class="text-sm text-[#39FF14] hover:text-[#00FFFF] flex items-center gap-1"
                target="_blank"
              >
                Github <github-icon class="w-4 h-4"/>
              </a>
            </div>
          </div>
        </div>
      </div>
      <!-- Ver Mais / Ver Menos -->
      <div v-if="projects.length > visibleCount" class="flex justify-end">
        <button 
          @click="showMore" 
          class="mt-4 text-[#39FF14] underline hover:text-[#00FFFF]"
        >
          Ver Mais
        </button>
      </div>

      <div v-if="visibleCount > 3" class="flex justify-end">
        <button 
          @click="showLess" 
          class="mt-4 text-[#39FF14] underline hover:text-[#00FFFF]"
        >
          Ver Menos
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectsSection',
  props: {
    projects: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      visibleCount: 3,
    };
  },
  computed: {
    visibleProjects() {
      return this.projects.slice(0, this.visibleCount);
    }
  },
  methods: {
    showMore() {
      this.visibleCount = this.projects.length;
    },
    showLess() {
      this.visibleCount = 3;
    }
  }
}
</script>

<style>
</style>
