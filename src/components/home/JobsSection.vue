<template>
  <section ref="jobs" id="jobs" class="py-20 bg-[#0A0A0A] relative overflow-hidden">
     <!-- Background Elements -->
    <div class="absolute top-1/2 left-1/2 w-[500px] h-[500px] bg-[#39FF14] opacity-5 rounded-full blur-[100px] -translate-x-1/2 -translate-y-1/2 pointer-events-none"></div>

    <div class="container mx-auto px-4 relative z-10">
      <h3 class="text-3xl md:text-4xl font-bold mb-16 text-[#00FFFF] text-center uppercase tracking-widest relative inline-block left-1/2 -translate-x-1/2">
        Freelance
        <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#00FFFF] to-[#39FF14]"></span>
      </h3>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="job in visibleJobs" 
          :key="job.id" 
          class="bg-[#2C2C2C]/30 backdrop-blur-sm border border-[#333] rounded-xl overflow-hidden group transition-all duration-300 hover:scale-[1.02] hover:border-[#39FF14]/50 hover:shadow-[0_0_20px_rgba(57,255,20,0.15)]"
          data-aos="fade-up"
        >
          <div class="aspect-video bg-[#0A0A0A] relative overflow-hidden">
             <div class="absolute inset-0 bg-[#39FF14]/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 z-10"></div>
            <img 
              :src="job.image" 
              :alt="job.title" 
              class="w-full h-full object-cover transition duration-500 group-hover:scale-110"
            />
          </div>
          
          <div class="p-6">
            <h4 class="text-xl font-bold mb-3 text-white group-hover:text-[#39FF14] transition-colors">{{ job.title }}</h4>
            <p class="text-sm text-gray-400 mb-6 leading-relaxed">{{ job.description }}</p>
            
            <div class="flex gap-2 pt-4 border-t border-white/5">
              <a 
                v-if="job.link" 
                :href="job.link" 
                class="text-sm font-bold text-white hover:text-[#39FF14] flex items-center gap-2 transition duration-300 bg-white/5 hover:bg-white/10 px-4 py-2 rounded-lg"
                target="_blank"
              >
                Acessar Projeto
                <external-link-icon class="w-4 h-4 transform group-hover:translate-x-1 transition duration-300"/>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Ver Mais / Ver Menos -->
      <div v-if="jobs.length > visibleCount || visibleCount > 3" class="flex justify-center mt-12">
        <button 
          v-if="jobs.length > visibleCount"
          @click="showMore" 
          class="px-8 py-3 bg-[#39FF14]/10 text-[#39FF14] border border-[#39FF14]/50 rounded-lg hover:bg-[#39FF14] hover:text-black font-bold uppercase tracking-wider transition-all duration-300"
        >
          Ver Mais Projetos
        </button>
         <button 
          v-else
          @click="showLess" 
          class="px-8 py-3 bg-white/5 text-gray-400 border border-white/10 rounded-lg hover:bg-white/10 hover:text-white font-bold uppercase tracking-wider transition-all duration-300"
        >
          Ver Menos
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'JobsSection',
  props: {
    jobs: {
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
    visibleJobs() {
      return this.jobs.slice(0, this.visibleCount);
    }
  },
  methods: {
    showMore() {
      this.visibleCount = this.jobs.length;
    },
    showLess() {
      this.visibleCount = 3;
    }
  }
}
</script>

<style>
</style>
