<template>
  <section ref="projects" id="projects" class="py-20 relative">
    <!-- Ambient mesh gradient background (optional) -->
     <div class="absolute top-0 right-0 w-[600px] h-[600px] bg-blue-500/5 rounded-full blur-[100px] -z-10 pointer-events-none"></div>

    <div class="container mx-auto px-4 relative z-10">
      <h3 class="text-3xl md:text-4xl font-bold mb-16 text-[#00FFFF] text-center uppercase tracking-widest relative inline-block left-1/2 -translate-x-1/2">
        Projetos
        <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#00FFFF] to-[#39FF14]"></span>
      </h3>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="project in visibleProjects" 
          :key="project.id" 
          class="group bg-white/5 backdrop-blur-sm border border-white/10 rounded-xl overflow-hidden transition-all duration-300 hover:-translate-y-2 hover:shadow-[0_10px_30px_-10px_rgba(0,255,255,0.15)] hover:border-[#00FFFF]/30"
          data-aos="fade-up"
        >
          <!-- Image Container -->
          <div class="aspect-video bg-[#050505] overflow-hidden relative">
            <div class="absolute inset-0 bg-[#00FFFF]/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 z-10"></div>
            <img 
              :src="project.image" 
              :alt="project.title" 
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
            />
          </div>

          <div class="p-6">
            <h4 class="text-xl font-bold mb-3 text-white group-hover:text-[#00FFFF] transition-colors">{{ project.title }}</h4>
            <p class="text-gray-400 text-sm mb-4 leading-relaxed line-clamp-3">{{ project.description }}</p>
            <p v-if="project.credentials" class="text-xs text-gray-500 mb-6 bg-black/30 p-2 rounded border border-white/5 font-mono">{{ project.credentials }}</p>
            
            <div class="flex gap-4 pt-4 border-t border-white/5">
              <a 
                v-if="project.demo" 
                :href="project.demo" 
                class="text-sm font-medium text-white hover:text-[#39FF14] flex items-center gap-2 transition duration-300"
                target="_blank"
              >
                Acessar 
                <external-link-icon class="w-4 h-4 transition-transform group-hover:translate-x-1"/>
              </a>
              <a 
                v-if="project.github" 
                :href="project.github" 
                class="text-sm font-medium text-white hover:text-[#39FF14] flex items-center gap-2 transition duration-300"
                target="_blank"
              >
                Github <github-icon class="w-4 h-4"/>
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Ver Mais / Ver Menos -->
      <div v-if="projects.length > visibleCount || visibleCount > 3" class="flex justify-center mt-12">
        <button 
          v-if="projects.length > visibleCount"
          @click="showMore" 
          class="text-sm font-bold uppercase tracking-widest text-[#39FF14] hover:text-[#00FFFF] border-b border-[#39FF14] hover:border-[#00FFFF] pb-1 transition-all"
        >
          Ver Todos os Projetos
        </button>
        <button 
          v-else
          @click="showLess" 
          class="text-sm font-bold uppercase tracking-widest text-gray-400 hover:text-white border-b border-gray-600 hover:border-white pb-1 transition-all"
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
