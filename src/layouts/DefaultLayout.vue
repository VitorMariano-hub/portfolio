<template>
  <div class="min-h-screen bg-[#0A0A0A] text-[#E0E0E0]">
    <app-header />
    <main>
      <slot></slot>
    </main>
    <app-footer />
  </div>
</template>

<script>
import AppHeader from '@/components/common/AppHeader.vue'
import AppFooter from '@/components/common/AppFooter.vue'

export default {
  name: 'DefaultLayout',
  components: {
    AppHeader,
    AppFooter
  }
}
</script>