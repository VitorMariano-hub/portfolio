<template>
    <footer class="bg-[#0A0A0A] border-t border-[#2C2C2C] py-8">
      <div class="container mx-auto px-4 text-center">
        <p>© {{ new Date().getFullYear() }} {{ name }}. Todos os direitos reservados.</p>
      </div>
    </footer>
</template>

<script>
export default {
  name: 'AppFooter',
  data() {
    return {
      name: 'Vitor Mariano'
    }
  }
}
</script>

<style>

</style>