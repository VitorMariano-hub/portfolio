<template>
  <nav class="fixed w-full backdrop-blur-md bg-[#0A0A0A]/80 border-b border-[#2C2C2C] z-50">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <a href="#"><h1 class="text-[#39FF14] text-xl font-bold hidden md:block">Vitor Mariano</h1></a>
      <div class="flex gap-6">
        <a
            v-for="item in menuItems"
            :key="item.href"
            href="#"
            @click.prevent="handleScrollTo(item.href)"
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
  props: {
    refsToScroll: Object,
  },
  data() {
    return {
      menuItems: [
      { text: 'Projetos', href: '#projects' },
      { text: 'Sobre', href: '#about' },
      { text: 'Experiências', href: '#experience' },
      { text: 'Contato', href: '#hero' }
    ]
    }
  },
  methods: {
  handleScrollTo(href) {
    if (href && href.startsWith('#')) {
      const id = href.substring(1);
      this.$emit('scroll-to', id);
    } else {
      console.warn('href não está corretamente definido:', href);
    }
  }
}

}
</script>
