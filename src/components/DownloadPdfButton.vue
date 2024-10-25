<template>
 <div>
    <button class="border border-[#39FF14] px-6 py-2 rounded hover:bg-[#00FFFF] hover:border-[#00FFFF] hover:text-black transition-colors" @click="downloadPdf">Currículo</button>
  </div>
</template>

<script>
export default {
  name: 'DownloadPdfButton',
  props: {
    pdfUrl: {
      type: String,
      required: true
    },
    pdfFileName: {
      type: String,
      required: true
    }
  },
  methods: {
    downloadPdf() {
      const link = document.createElement('a');
      link.href = this.pdfUrl;
      link.target = '_blank';
      link.download = this.pdfFileName;

      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }
  }
}
</script>

<style></style>
