<template>
  <section ref="jobs" id="jobs" class="py-20">
    <div class="container mx-auto px-4">
      <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Freelance</h3>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="job in visibleJobs" 
          :key="job.id" 
          class="bg-[#2C2C2C] rounded-md overflow-hidden group transition-transform duration-300 hover:scale-[1.02]"
          data-aos="fade-up"
        >
          <div class="aspect-video bg-[#0A0A0A]">
            <img 
              :src="job.image" 
              :alt="job.title" 
              class="w-full h-full object-cover transition duration-300 group-hover:opacity-80"
            />
          </div>
          <div class="p-4">
            <h4 class="text-xl font-bold mb-2">{{ job.title }}</h4>
            <p class="text-sm mb-4 ">{{ job.description }}</p>
            <div class="flex gap-2">
              <a 
                v-if="job.link" 
                :href="job.link" 
                class="text-sm text-[#39FF14] hover:text-[#00FFFF] flex items-center gap-1 transition duration-300"
                target="_blank"
              >
                Acessar 
                <external-link-icon class="w-4 h-4 transform group-hover:translate-x-1 transition duration-300"/>
              </a>
            </div>
          </div>
        </div>
      </div>
      <!-- Ver Mais / Ver Menos -->
      <div v-if="jobs.length > visibleCount" class="flex justify-end">
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
