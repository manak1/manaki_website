<template>
  <div>
    <c-hero />
    <c-about />
  </div>
</template>

<script>
import CHero from '@/pages/-CHero'
import CAbout from '@/pages/-CAbout'
export default {
  components: {
    CHero,
    CAbout
  }
}
</script>
