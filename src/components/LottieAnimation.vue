<template>
  <div ref="lottieContainer" class="lottie-animation"></div>
</template>

<script>
import lottie from 'lottie-web'

export default {
  name: 'LottieAnimation',
  props: {
    animationData: {
      type: Object,
      required: true
    }
  },
  mounted() {
    this.animation = lottie.loadAnimation({
      container: this.$refs.lottieContainer,
      renderer: 'svg',
      loop: true,
      autoplay: true,
      animationData: this.animationData
    })
  },
  beforeDestroy() {
    if (this.animation) {
      this.animation.destroy()
    }
  }
}
</script>

<style scoped>
.lottie-animation {
  width: 100%;
  height: 100%;
}
</style>
