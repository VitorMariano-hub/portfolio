<template>
  <div class="app">
    <HomeView />
  </div>
</template>

<script>
import HomeView from '@/views/HomeView.vue'
export default {
  name: 'App',
  components: {
    HomeView
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
    Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #0A0A0A;
  color: #E0E0E0;
}

.app {
  min-height: 100vh;
  overflow-x: hidden;
}
</style>
