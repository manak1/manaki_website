<template>
  <client-only>
    <full-page id="fullpage" :options="options">
      <div class="section fp-table active">
        <c-hero />
      </div>
      <div class="section fp-table active">
        <c-work />
      </div>
      <div class="section fp-table active">
        <c-about />
      </div>
    </full-page>
  </client-only>
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
      options: {
        licenseKey: 'OPEN-SOURCE-GPLV3-LICENSE',
        scrollBar: false,
        menu: '#menu',
        navigation: true,
        easingcss3: 'cubic-bezier(0.77, 0.2, 0.05, 1)',
        anchors: ['#home', '#about', 'work'],
        sectionsColor: [
          '#41b883',
          '#ff5f45',
          '#0798ec',
          '#fec401',
          '#1bcee6',
          '#ee1a59',
          '#2c3e4f',
          '#ba5be9',
          '#b4b8ab'
        ]
      }
    }
  }
}
</script>
