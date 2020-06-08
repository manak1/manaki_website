<template>
  <div>
    <!--     <l-header /> -->
    <nuxt />
    <cursor-fx color="#fff" color-hover="#fff" />
    <div class="p-loader"></div>
  </div>
</template>

<script>
/* import LHeader from '@/components/layout/LHeader' */
export default {
  components: {
    /*  LHeader */
  },
  mounted() {
    const tl = this.$gsap.timeline({
      repeat: 0
    })
    tl.to('.p-loader', 1.4, {
      y: '-100vh',
      ease: 'Power3.easeIn'
    })
  }
}
</script>

<style lang="scss">
body {
  font-family: futura-pt, sans-serif;
}

.p-loader {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100vh;
  background-color: #fff;
  z-index: 999;
}
</style>
