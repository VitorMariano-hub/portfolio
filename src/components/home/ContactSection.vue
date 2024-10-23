<template>
  <section id="contact" class="py-20 bg-[#2C2C2C]">
      <div class="container mx-auto px-4">
        <h3 class="text-3xl font-bold mb-8 text-[#00FFFF]">Contato</h3>
        <div class="max-w-xl mx-auto">
          <form @submit.prevent="handleSubmit" class="space-y-4">
            <div>
              <label class="block mb-2">Nome</label>
              <input 
                v-model="form.name"
                type="text" 
                class="w-full bg-[#0A0A0A] border border-[#C0C0C0]/20 rounded px-4 py-2 focus:outline-none focus:border-[#39FF14]" 
              />
            </div>
            <div>
              <label class="block mb-2">Email</label>
              <input 
                v-model="form.email"
                type="email" 
                class="w-full bg-[#0A0A0A] border border-[#C0C0C0]/20 rounded px-4 py-2 focus:outline-none focus:border-[#39FF14]" 
              />
            </div>
            <div>
              <label class="block mb-2">Mensagem</label>
              <textarea 
                v-model="form.message"
                class="w-full bg-[#0A0A0A] border border-[#C0C0C0]/20 rounded px-4 py-2 focus:outline-none focus:border-[#39FF14] h-32" 
              />
            </div>
            <button 
              type="submit"
              class="w-full bg-[#39FF14] text-black py-2 rounded hover:bg-[#00FFFF] transition-colors"
            >
              Enviar Mensagem
            </button>
          </form>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  name: 'ContactSection',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    handleSubmit() {
      console.log(this.form)
    }
  }
}
</script>

<style>

</style>