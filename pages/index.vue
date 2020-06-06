<template>
  <div class="fullpage-container">
    <div class="fullpage-wp">
      <c-hero />
      <c-work />
      <c-about />
    </div>
  </div>
</template>

<script>
import CHero from '@/pages/-CHero'
import CAbout from '@/pages/-CAbout'
import CWork from '@/pages/-CWork'
export default {
  components: {
    CHero,
    CAbout,
    CWork
  },
  data() {
    return {
      scrollY: 0,
      moving: false
    }
  }
}
</script>
