<template>
  <div class="min-h-screen bg-[#0A0A0A] text-[#E0E0E0]">
    <app-header @scroll-to="scrollToSection" />
    <main>
      <slot></slot>
    </main>
    <app-footer />
  </div>
</template>

<script>
import AppHeader from '@/components/common/AppHeader.vue'
import AppFooter from '@/components/common/AppFooter.vue'
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'DefaultLayout',
  components: {
    AppHeader,
    AppFooter
  },
  mounted() {
    AOS.init();
  },
  methods: {
  scrollToSection(id) {
    const el = document.getElementById(id);
    if (el) {
      el.scrollIntoView({ behavior: 'smooth' });
    } else {
      console.warn('Elemento não encontrado:', id);
    }
  }
}
}
</script>