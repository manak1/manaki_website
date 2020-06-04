<template>
  <header class="w-full fixed  text-white">
    <nav class="px-10 pt-8 mx-auto flex justify-between">
      <h1 class="font-bold">MANAKI / IKEDA</h1>
      <div class="logo font-bold">
        <ol class="flex relative">
          <li class="text-white ">
            <nuxt-link to="/" class="px-5">Home</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5">About</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5">Work</nuxt-link>
          </li>
          <li class="text-white ">
            <nuxt-link to="/" class="px-5">Contact</nuxt-link>
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

  &__lineHome {
    left: 17px;
  }
}
</style>
