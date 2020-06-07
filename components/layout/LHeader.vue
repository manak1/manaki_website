<template>
  <header class="w-full fixed l-header text-white">
    <nav class="px-10 pt-8 mx-auto flex justify-between">
      <h1 class="font-bold l-header__title" data-cursor-hover>
        MANAKI / IKEDA
      </h1>
      <div class="logo font-bold">
        <ol class="flex relative">
          <li class="text-white ">
            <nuxt-link to="/" class="px-5" data-cursor-hover>Home</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link
              class="px-5"
              to="/"
              data-cursor-hover
              @click.native="pushAbout()"
              >About</nuxt-link
            >
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5" data-cursor-hover>Work</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5" data-cursor-hover>Social</nuxt-link>
          </li>
          <li
            class="l-header__line l-header__lineHome"
            :class="actionClass"
          ></li>
        </ol>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  computed: {
    getQuery() {
      return this.$route.hash
    },
    actionClass() {
      return {
        'c-home__active': this.getQuery === '#home',
        'c-about__active': this.getQuery === '#about',
        'c-work__active': this.getQuery === '#work'
      }
    }
  },
  mounted() {},
  methods: {
    handleSmooth() {
      event.preventDefault()
      this.$SmoothScroll(document.querySelector('#work'), 1200, null, null, 'y')
    },
    pushAbout() {
      this.$router.push('#about')

      /* 
      use this https://github.com/alvarotrigo/vue-fullpage.js
      */
    }
  }
}
</script>

<style lang="scss">
.l-header {
  z-index: 999;
  &__line {
    position: absolute;
    width: 52px;
    height: 2px;
    bottom: -8px;
    background-color: #fff;
  }

  &__title {
    letter-spacing: initial;
    transition-duration: 0.2s;
    transition-timing-function: ease-in-out;

    &:hover {
      letter-spacing: 2px;
      transition-duration: 0.2s;
      transition-timing-function: ease-in-out;
    }
  }

  &__lineHome {
    left: 17px;
    transition: 0.9s cubic-bezier(0.785, 0.135, 0.15, 0.86);
  }
}

.c-home__active {
  left: 17px;
  transition-duration: 0.9s;
}

.c-about__active {
  left: 100px;
  transition-duration: 0.9s;
}

.c-work__active {
  left: 180px;
}
</style>
