<template>
  <div class="p-hero">
    <div class="mx-auto container h-screen flex flex-col p-hero__container">
      <div class="p-hero__spacer flex-grow h-12"></div>
      <div class="p-hero__logo inline-block w-2/5 mx-auto text-center">
        <p class="p-hero__name p-hero__ma">MA</p>
        <p class="p-hero__name p-hero__n">N</p>
        <p class="p-hero__name p-hero__ak">
          <span class="p-hero__akCenter">A</span>
        </p>
        <p class="p-hero__name p-hero__i">I</p>
        <img
          src="@/assets/images/hero/hero_logo.png"
          alt="ウェブサイトのロゴ"
          class="mx-auto w-full p-hero__img"
        />
      </div>
      <div class="p-hero__spacer flex-grow h-12"></div>
      <div
        class="text-center inline-block mx-auto mt-12 pb-6 relative p-hero__attention "
      >
        <a
          class="text-sm"
          href="#"
          data-cursor-hover
          :class="actionClass"
          @click.prevent="$refs.fullpage.api.moveSectionDown()"
          >Scroll to discover
          <div class="relative h-8 mt-2 " :class="actionClass">
            <div class="p-hero__bar mx-auto mt-2"></div>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import CSSRulePlugin from 'gsap/CSSRulePlugin'

export default {
  data() {
    return {
      visible: true,
      scrollY: 0
    }
  },
  computed: {
    actionClass() {
      return {
        'c-scrolled': this.$route.hash !== '#home'
      }
    }
  },
  mounted() {
    this.$gsap.registerPlugin(CSSRulePlugin)
    this.logoAniamtion()
  },
  methods: {
    logoAniamtion() {
      const bar1 = CSSRulePlugin.getRule('.p-hero__ma:after')
      const bar2 = CSSRulePlugin.getRule('.p-hero__n:after')
      const bar3 = CSSRulePlugin.getRule('.p-hero__ak:after')
      const timingText = 0.8
      const timingBar = 0.7
      const tl = this.$gsap.timeline({
        repeat: 0
      })
      tl.delay(2)
      tl.from('.p-hero__ma', timingText, {
        opacity: '0',
        scale: '1.6',
        ease: 'Power2.easeInOut'
      })
      tl.from(bar1, timingBar, { width: '0%', ease: 'Power2.easeInOut' }, 1)
      tl.from('.p-hero__n', timingText, {
        opacity: '0',
        scale: '1.6',
        ease: 'Power2.easeInOut'
      })
      tl.from(bar2, timingBar, { height: '0%', ease: 'Power2.easeInOut' })
      tl.from('.p-hero__ak', timingText, {
        opacity: '0',
        scale: '1.6',
        ease: 'Power2.easeInOut'
      })
      tl.from(bar3, timingBar, { width: '0%', ease: 'Power2.easeInOut' })
      tl.from('.p-hero__i', timingText, {
        opacity: '0',
        scale: '1.6',
        ease: 'Power2.easeInOut'
      })
      tl.from('.p-hero__img', {
        opacity: '0',
        scale: '1.5',
        ease: 'Power2.easeInOut'
      })

      tl.from('.p-hero__attention', 3, { opacity: '0', ease: 'easeInOut' })
    }
  }
}
</script>

<style lang="scss">
$bar-color: #fff;

.p-hero {
  background-color: #f8f8f8;
  background-color: #191919;
  color: #fff;
  overflow: hidden;

  &__logo {
    position: relative;
  }

  &__img {
    z-index: 3;
  }

  &__name {
    position: absolute;
    font-weight: bold;
    font-size: 42px;
    z-index: 1;
  }

  &__ma {
    left: -20px;
    width: 100%;
    text-align: left;

    &:after {
      position: absolute;
      left: 80px;
      top: 30px;
      content: '';
      width: 80%;
      height: 2px;
      background-color: $bar_color;
      display: block;
    }
  }

  &__n {
    right: -20px;
    height: 80%;

    &:after {
      position: absolute;
      left: 14px;
      top: 75px;
      content: '';
      width: 2px;
      height: 90%;
      background-color: $bar_color;
      display: block;
    }
  }

  &__ak {
    width: 100%;
    text-align: right;
    letter-spacing: -12px;
    right: -3px;
    bottom: 30px;

    &:after {
      position: absolute;
      right: 30px;
      top: 53px;
      content: '';
      width: 90%;
      height: 2px;
      background-color: $bar_color;
      display: block;
    }

    &:before {
      content: 'K';
      position: absolute;
      top: 40px;
    }
  }

  &__akCenter {
    margin-left: auto;
  }

  &__i {
    bottom: 13px;
    left: -20px;
  }

  &__bar {
    width: 1px;
    height: 32px;
    position: absolute;
    left: 50%;
    margin-top: 20px;
    background-color: $bar_color;
    animation: scrollDown 2s infinite;
    animation-timing-function: cubic-bezier(0.785, 0.135, 0.15, 0.86);
  }

  &__attention {
    opacity: 1;
  }
}

.c-scrolled {
  opacity: 0;
  transition-duration: 0.3s;
}

@keyframes scrollDown {
  0% {
    bottom: 100%;
    height: 0;
  }
  50% {
    bottom: 0;
    height: 100%;
  }

  100% {
    bottom: 0;
    height: 0;
  }
}
</style>
