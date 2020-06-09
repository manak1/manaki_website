<template>
  <div>
    <l-header @jumpSection="jumpSection" />
    <client-only>
      <full-page id="fullpage" ref="fullpage" :options="options">
        <div class="section">
          <c-hero />
        </div>
        <div class="section">
          <c-work />
        </div>
        <div class="section">
          <c-about />
        </div>
      </full-page>
    </client-only>
  </div>
</template>

<script>
import CHero from '@/pages/-CHero'
import CAbout from '@/pages/-CAbout'
import CWork from '@/pages/-CWork'
import LHeader from '@/components/layout/LHeader'
export default {
  components: {
    CHero,
    CAbout,
    CWork,
    LHeader
  },
  data() {
    return {
      sections: ['home', 'work', 'about'],
      index: 0,
      options: {
        licenseKey: 'OPEN-SOURCE-GPLV3-LICENSE',
        scrollBar: false,
        navigation: false,
        easingcss3: 'cubic-bezier(0.77, 0.2, 0.05, 1)',
        anchors: ['home', 'work', 'about'],
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
  },
  methods: {
    jumpSection(index) {
      this.$refs.fullpage.api.moveTo(index)
    }
  }
}
</script>
