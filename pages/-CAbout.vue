<template>
  <section class="c-about h-screen text-white flex flex-col ">
    <div class="flex-grow"></div>
    <div class="container px-10 mx-auto text-center">
      <div class="c-head">
        <h2 class="c-head__title text-white">ABOUT</h2>
      </div>
      <div class="flex justify-center w-full items-center mx-auto c-about__box">
        <div class="w-1/2 c-box ">
          <img
            data-cursor-hover
            src="@/assets/images/about/about_me.JPG"
            class="c-box__img"
            alt=""
          />
        </div>
        <div class="w-1/2 c-profile text-left">
          <h3 class="c-profile__job ">
            Frontend Engineer
          </h3>
          <p class="c-profile__text">
            池田愛樹と申します。Nuxt.jsを使ったウェブサイト制作が得意でフロントエンド周りに興味があります。
            1997年生まれ、兵庫県立国際高校卒 株式会社chatbox所属。The
            FWA審査員。Webデザイナー/フロントエンドエンジニアとしてキャリアをスタートし、現在はアートディレクションや、動画やスチールのディレクション、UIデザイン、空間デザイン、フロントエンドエンジニアリングなど、多岐に活躍。自身が運営を務めるWebデザインギャラリー
            S5-Styleでは優れたWebデザインを日々キュレーションしている。
          </p>
          <a class="border px-8 py-2  inline-block  mt-6 ">see more</a>
        </div>
      </div>
    </div>
    <div class="flex-grow"></div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.c-about {
  padding-bottom: 240px;
  background-color: #191919;

  &__job {
    font-size: 46px;
  }

  &__title {
    font-size: 12px;
  }

  &__box {
    padding-top: 56px;
  }
}

.c-box {
  margin-right: 40px;
  &__img {
    max-width: 320px;
    margin-left: auto;
    filter: grayscale(100%);
    transition-duration: 0.3s;
    transition-timing-function: ease-in;
    &:hover {
      filter: grayscale(0%);
      transition-duration: 0.3s;
      transition-timing-function: ease-out;
    }
  }
}

.c-profile {
  &__job {
    font-weight: 700;
    font-size: 32px;
    font-style: italic;
  }

  &__text {
    margin-top: 16px;
    text-align: left;
    font-size: 16px;
    max-width: 420px;
  }
}
</style>
