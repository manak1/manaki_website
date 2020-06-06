<template>
  <header class="w-full fixed  text-white">
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
            <nuxt-link to="/" class="px-5" data-cursor-hover>About</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5" data-cursor-hover>Work</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5" data-cursor-hover>Contact</nuxt-link>
          </li>
          <li class="l-header__line l-header__lineHome"></li>
        </ol>
      </div>
    </nav>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss">
.l-header {
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
  }
}
</style>
