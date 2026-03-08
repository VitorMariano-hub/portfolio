<template>
  <section ref="contact" id="contact" class="py-20 bg-[#0A0A0A] relative overflow-hidden">
      <!-- Background Elements -->
      <div class="absolute bottom-0 right-0 w-96 h-96 bg-[#39FF14] opacity-5 rounded-full blur-3xl translate-y-1/2 translate-x-1/2"></div>
      
      <div class="container mx-auto px-4 relative z-10">
        <h3 class="text-3xl md:text-4xl font-bold mb-16 text-[#00FFFF] text-center uppercase tracking-widest relative inline-block left-1/2 -translate-x-1/2">
          Contato
          <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#00FFFF] to-[#39FF14]"></span>
        </h3>
        
        <div class="max-w-xl mx-auto bg-[#2C2C2C]/30 backdrop-blur-sm p-8 rounded-xl border border-[#333] shadow-[0_0_20px_rgba(0,0,0,0.5)]">
          <form @submit.prevent="handleSubmit" class="space-y-6">
            <div>
              <label class="block mb-2 text-gray-300 font-medium">Nome</label>
              <input 
                v-model="form.name"
                type="text" 
                class="w-full bg-[#0A0A0A]/50 border border-[#333] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#39FF14] focus:ring-1 focus:ring-[#39FF14] transition-all"
                placeholder="Seu nome"
              />
            </div>
            <div>
              <label class="block mb-2 text-gray-300 font-medium">Email</label>
              <input 
                v-model="form.email"
                type="email" 
                class="w-full bg-[#0A0A0A]/50 border border-[#333] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#39FF14] focus:ring-1 focus:ring-[#39FF14] transition-all"
                 placeholder="seu@email.com"
              />
            </div>
            <div>
              <label class="block mb-2 text-gray-300 font-medium">Mensagem</label>
              <textarea 
                v-model="form.message"
                class="w-full bg-[#0A0A0A]/50 border border-[#333] rounded-lg px-4 py-3 text-white focus:outline-none focus:border-[#39FF14] focus:ring-1 focus:ring-[#39FF14] transition-all h-32 resize-none"
                placeholder="Sua mensagem..."
              />
            </div>
            <button 
              type="submit"
              class="w-full bg-[#39FF14] text-black font-bold py-3 rounded-lg hover:bg-[#32e012] transition-all duration-300 transform hover:-translate-y-1 hover:shadow-[0_0_20px_rgba(57,255,20,0.4)]"
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