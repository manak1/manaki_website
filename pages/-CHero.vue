<template>
  <div class="p-hero">
    <div class="mx-auto container h-screen flex flex-col">
      <div class="p-hero__spacer flex-grow h-12"></div>
      <div class="p-hero__logo inline-block w-2/5 mx-auto text-center">
        <p class="p-hero__name">MA</p>
        <p class="p-hero__name">N</p>
        <p class="p-hero__name">AK</p>
        <p class="p-hero__name">I</p>
        <img
          src="@/assets/images/hero/hero_logo.png"
          alt="ウェブサイトのロゴ"
          class="mx-auto w-full p-hero__img"
        />
      </div>
      <div class="p-hero__spacer flex-grow h-12"></div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.p-hero {
  background-color: #f8f8f8;

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

    &:nth-child(1) {
      left: -20px;

      &:after {
        position: absolute;
        left: 80px;
        top: 30px;
        content: '';
        width: 420px;
        height: 2px;
        background-color: #000;
        display: block;
      }
    }

    &:nth-child(2) {
      right: -20px;

      &:after {
        position: absolute;
        left: 14px;
        top: 75px;
        content: '';
        width: 2px;
        height: 330px;
        background-color: #000;
        display: block;
      }
    }

    &:nth-child(3) {
      writing-mode: vertical-lr;
      text-orientation: upright;
      letter-spacing: -12px;
      right: -35px;
      bottom: 30px;

      &:after {
        position: absolute;
        left: -470px;
        top: 63px;
        content: '';
        width: 470px;
        height: 2px;
        background-color: #000;
        display: block;
      }
    }

    &:nth-child(4) {
      bottom: 13px;
      left: -20px;
    }
  }
}
</style>
