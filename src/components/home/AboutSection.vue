<template>
  <section id="about" class="py-20 bg-[#2C2C2C]">
      <div class="container mx-auto px-4">
        <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Sobre Mim</h3>
        <div class="grid md:grid-cols-2 gap-8">
          <div class="space-y-4">
            <p v-for="(paragraph, index) in about" :key="index">{{ paragraph }}</p>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <div v-for="skill in skills" :key="skill.title" class="bg-[#0A0A0A] p-4 rounded">
              <component :is="skill.icon" class="w-8 h-8 text-[#39FF14] mb-2"/>
              <h4 class="font-bold mb-2">{{ skill.title }}</h4>
              <p class="text-sm">{{ skill.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  name: 'AboutSection',
  props: {
    about: {
      type: Array,
      required: true
    },
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>

</style>