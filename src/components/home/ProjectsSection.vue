<template>
  <section id="projects" class="py-20">
      <div class="container mx-auto px-4">
        <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Projetos</h3>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div 
            v-for="project in projects" 
            :key="project.id" 
            class="bg-[#2C2C2C] rounded-md overflow-hidden  group"
          >
            <div class="aspect-video bg-[#0A0A0A]">
              <img :src="project.image" :alt="project.title" class="w-full h-full object-cover"/>
            </div>
            <div class="p-4">
              <h4 class="text-xl font-bold mb-2">{{ project.title }}</h4>
              <p class="text-sm mb-4">{{ project.description }}</p>
              <p class="text-sm mb-2">{{ project.credentials }}</p>
              <div class="flex gap-2">
                <a 
                  v-if="project.demo" 
                  :href="project.demo" 
                  class="text-sm text-[#39FF14] hover:text-[#00FFFF] flex items-center gap-1"
                  target="_blank"
                >
                  Demo <external-link-icon class="w-4 h-4"/>
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
  }
}
</script>

<style>

</style>