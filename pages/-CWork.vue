<template>
  <section class="c-work text-white pt-24 pb-12">
    <div class="container text-center mx-auto">
      <div class="c-work__head">
        <h2>/ WORK /</h2>
        <div>
          <carousel>
            <slide> <img src="@/assets/images/work/work1.png" alt=""/></slide>
            <slide> <img src="@/assets/images/work/work1.png" alt=""/></slide>
            <slide> <img src="@/assets/images/work/work1.png" alt=""/></slide>
          </carousel>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Carousel from 'vue-carousel/src/Carousel.vue'
import Slide from 'vue-carousel/src/Slide.vue'
export default {
  components: {
    Carousel,
    Slide
  }
}
</script>

<style lang="scss" scoped>
.c-work {
  background-color: #191919;
}
</style>
