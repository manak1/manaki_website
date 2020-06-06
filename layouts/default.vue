<template>
  <div>
    <l-header />
    <nuxt />
    <cursor-fx color="#fff" color-hover="#fff" />
  </div>
</template>

<script>
import LHeader from '@/components/layout/LHeader'
export default {
  components: {
    LHeader
  }
}
</script>

<style lang="scss">
body {
  font-family: futura-pt, sans-serif;
}
</style>
