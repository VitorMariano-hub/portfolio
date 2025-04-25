<template>
  <nav class="fixed w-full backdrop-blur-md bg-[#0A0A0A]/80 border-b border-[#2C2C2C] z-50">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <!-- Logo -->
      <a href="#" @click.prevent="handleScrollTo('hero')">
        <h1 class="text-[#39FF14] text-xl font-bold">Vitor Mariano</h1>
      </a>

      <!-- Menu Desktop -->
      <div class="hidden md:flex gap-8">
        <a
          v-for="item in menuItems"
          :key="item.href"
          href="#"
          @click.prevent="handleScrollTo(item.href)"
          class="text-white hover:text-[#39FF14] relative transition-colors"
        >
          <span class="after:block after:absolute after:w-0 after:h-[2px] after:bg-[#39FF14] after:bottom-0 after:left-0 after:transition-all after:duration-300 hover:after:w-full">
            {{ item.text }}
          </span>
        </a>
      </div>

      <!-- Ícone hamburger -->
      <button @click="isMenuOpen = true" class="md:hidden text-white focus:outline-none text-2xl">
        ☰
      </button>
    </div>

    <!-- Menu Mobile (Drawer) -->
    <transition name="fade">
      <div
        v-if="isMenuOpen"
        class="fixed top-20 left-0 w-full h-full bg-black bg-opacity-80 z-40 flex items-center justify-center"
      >
        <div class="bg-[#0A0A0A] rounded-lg p-8 space-y-6 w-11/12 max-w-sm text-center">
          <!-- Botão fechar -->
          <button @click="isMenuOpen = false" class="absolute top-6 right-6 text-white text-4xl z-50">
            &times;
          </button>

          <div class="flex flex-col gap-6">
            <a
              v-for="item in menuItems"
              :key="item.href"
              href="#"
              @click.prevent="handleScrollAndClose(item.href)"
              class="text-white text-lg hover:text-[#39FF14] transition-colors"
            >
              {{ item.text }}
            </a>
          </div>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script>
export default {
  props: {
    refsToScroll: Object,
  },
  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { text: 'Projetos', href: '#projects' },
        { text: 'Sobre', href: '#about' },
        { text: 'Experiências', href: '#experience' },
        { text: 'Contato', href: '#hero' }
      ]
    };
  },
  methods: {
    handleScrollTo(href) {
      if (href && href.startsWith('#')) {
        const id = href.substring(1);
        this.$emit('scroll-to', id);
      }
    },
    handleScrollAndClose(href) {
      this.handleScrollTo(href);
      this.isMenuOpen = false;
    }
  }
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
