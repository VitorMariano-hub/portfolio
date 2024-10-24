<template>
    <nav class="fixed w-full backdrop-blur-md bg-[#0A0A0A]/80 border-b border-[#2C2C2C] z-50">
      <div class="container mx-auto px-4 py-4 flex justify-between items-center">
        <a href="#"><h1 class="text-[#39FF14] text-xl font-bold">Vitor Mariano</h1></a>
        <div class="flex gap-6">
          <a 
            v-for="item in menuItems" 
            :key="item.href" 
            :href="item.href"
            class="hover:text-[#39FF14] transition-colors"
          >
            {{ item.text }}
          </a>
        </div>
      </div>
    </nav>
</template>

<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      menuItems: [
        {
          text: 'Sobre',
          href: '#about'
        },
        {
          text: 'Projetos',
          href: '#projects'
        },
        {
          text: 'Experiências',
          href: '#experience'
        },
        {
          text: 'Contato',
          href: '#contact'
        }
      ]
    }
  }
}
</script>

<style>

</style>