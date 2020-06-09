<template>
  <section class="c-work  text-white">
    <div class="container h-screen px-10 text-center mx-auto flex flex-col">
      <div class="flex-grow"></div>
      <div class="c-work__head">
        <h2>WORK</h2>
        <p>{{ index }}</p>
        <div class="c-slider">
          <div class="c-slider__item justify-center flex items-center">
            <div class="c-desc w-2/5">
              <div class="overflow-hidden">
                <h3 class="c-desc__title">{{ getWork.title }}</h3>
              </div>
              <div class="overflow-hidden">
                <span class="c-desc__category"
                  ><span class="c-desc__categoryBar" />{{ getWork.tag }}</span
                >
              </div>
              <div class="overflow-hidden">
                <p class="c-desc__text">
                  {{ getWork.text }}
                </p>
              </div>
            </div>
            <div class="c-item w-3/5">
              <a :href="getWork.url" target="_blank">
                <img
                  :src="getWork.img"
                  alt="制作物の画像"
                  class="c-item__img"
                />
              </a>
            </div>
          </div>
          <div class="c-slider__left">
            <a
              class="c-slider__cursor block"
              @click.prevent="previousProject()"
            >
              <img
                class="c-slider__icon"
                src="@/assets/images/work/arrow_left.svg"
                alt="一つ戻る"
              />
            </a>
          </div>
          <div class="c-slider__right">
            <a href="#" class="c-slider__cursor">
              <img
                class="c-slider__icon"
                src="@/assets/images/work/arrow_right.svg"
                alt="一つ進む"
                @click.prevent="nextProject()"
              />
            </a>
          </div>
        </div>
        <div class="c-buttons mt-24">
          <a
            class="c-buttons__buttonm border px-8 py-2 inline-block"
            @click.prevent="animation_in()"
          >
            see more
          </a>
        </div>
      </div>
      <div class="flex-grow"></div>
    </div>
  </section>
</template>

<script>
import { CSSRulePlugin } from 'gsap/CSSRulePlugin'
import { works } from '@/static/api/works.json'
export default {
  data() {
    return {
      workData: works,
      index: 0
    }
  },
  computed: {
    getWork() {
      return this.workData[this.index]
    }
  },
  methods: {
    nextProject() {
      if (this.index + 1 >= this.workData.length) {
        this.index = 0
      } else {
        this.index = this.index + 1
      }
    },
    previousProject() {
      if (this.index - 1 < 0) {
        this.index = this.workData.length - 1
      } else {
        this.index = this.index - 1
      }
    },
    /* 
    横から白いボックスが出てきて表示する
    消える時も同じく白いボックス消えて↑
    */
    animation_in() {
      // black covers
      const titleHide = CSSRulePlugin.getRule('.c-desc__title:after')
      const textHide = CSSRulePlugin.getRule('.c-desc__text:after')
      const tagHide = CSSRulePlugin.getRule('.c-desc__category:after')
      // white covers
      const titleHide2 = CSSRulePlugin.getRule('.c-desc__title:before')
      const textHide2 = CSSRulePlugin.getRule('.c-desc__text:before')
      const tagHide2 = CSSRulePlugin.getRule('.c-desc__category:before')

      const tl = this.$gsap.timeline({
        repeat: 0
      })
      tl.to(titleHide, 0.8, { width: '0%', ease: 'Power3.easeInOut' }, 1)
      tl.to(textHide, 0.8, { width: '0%', ease: 'Power3.easeInOut' }, 1)
      tl.to(tagHide, 0.8, { width: '0%', ease: 'Power3.easeInOut' }, 1)

      tl.to(titleHide2, 0.6, { width: '0%', ease: 'Power1.easeInOut' }, 2)
      tl.to(textHide2, 0.6, { width: '0%', ease: 'Power1.easeInOut' }, 2)
      tl.to(tagHide2, 0.6, { width: '0%', ease: 'Power1.easeInOut' }, 2)
    }
  }
}
</script>

<style lang="scss">
.c-work {
  background-color: #191919;
}

.c-slider {
  position: relative;
  padding-top: 56px;
  &__item {
    padding: 0 140px;
  }

  &__left {
    position: absolute;
    left: 3%;
    top: 50%;
    transform: translateY(-50%);
  }

  &__right {
    position: absolute;
    right: 3%;
    top: 50%;
    transform: translateY(-50%);
  }

  &__icon {
    width: 30px;
    height: 70px;
    margin: 0 auto;
    transition: 0.2s;
    transition-timing-function: ease-out;
  }

  &__cursor {
    position: relative;
    display: inline-block;
    border: 1px solid #fff;
    border-radius: 50%;
    line-height: 0.8;
    width: 70px;
    height: 70px;
    line-height: 70px;
    font-size: 40px;

    &:nth-child(1) {
      &::after {
        position: absolute;
        top: 50%;
        opacity: 0;
        content: 'before';
        height: 2px;
        display: inline-block;
      }
    }

    &:hover {
      position: relative;

      .c-slider__icon {
        transform: translateX(-60px);
        transition: 0.2s;
        transition-timing-function: ease-out;
      }

      &::after {
        left: -30px;
        animation: arrowBar 0.7s 1;
        animation-fill-mode: forwards;
        opacity: 1;
        animation-timing-function: ease-in-out;
      }
    }
  }
}

.c-item {
  max-width: 576px;
  filter: grayscale(100%);
  transition-duration: 3s;
  transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1),
    cubic-bezier(0.215, 0.61, 0.355, 1);

  &:hover {
    filter: grayscale(0%);
    transition-duration: 3s;
    transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1),
      cubic-bezier(0.215, 0.61, 0.355, 1);
  }

  &__img {
    height: 328px;
    width: 520px;
    object-fit: contain;
  }
}

.c-desc {
  margin-right: 40px;
  text-align: left;
  max-width: 320px;
  &__title {
    position: relative;
    font-size: 24px;
    font-weight: bold;

    &:after {
      position: absolute;
      right: 0;
      top: 0;
      content: '';
      width: 100%;
      height: 30px;
      background-color: #191919;
      display: inline-block;
      z-index: 999;
    }

    &:before {
      position: absolute;
      right: 0;
      top: 0;
      content: '';
      width: 100%;
      height: 30px;
      background-color: #fff;
      display: inline-block;
      z-index: 999;
    }
  }

  &__text {
    position: relative;
    margin-top: 12px;
    font-size: 16px;
    line-height: 2;

    &:after {
      position: absolute;
      right: 0px;
      top: 0;
      content: '';
      width: 100%;
      height: 100%;
      background-color: #191919;
      display: inline-block;
      z-index: 999;
    }

    &:before {
      position: absolute;
      right: 0;
      top: 0;
      content: '';
      width: 100%;
      height: 100%;
      background-color: #fff;
      display: inline-block;
      z-index: 999;
    }
  }

  &__category {
    position: relative;
    display: inline-block;
    margin: 12px;

    &:before {
      position: absolute;
      right: 0;
      top: 0;
      content: '';
      width: 100%;
      height: 30px;
      background-color: #fff;
      display: inline-block;
      z-index: 999;
    }

    &:after {
      position: absolute;
      right: -10px;
      top: 0;
      content: '';
      width: 140%;
      height: 30px;
      background-color: #191919;
      display: inline-block;
      z-index: 999;
    }
  }

  &__categoryBar {
    width: 4px;
    height: 20px;
    background-color: #fff;
    position: absolute;
    left: -12px;
    top: 2px;
  }
}

@keyframes arrowBar {
  0% {
    width: 0px;
  }

  50% {
    width: 120px;
  }

  100% {
    width: 200px;
  }
}
</style>
