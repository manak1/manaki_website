<template>
  <section class="c-work text-white">
    <div class="container text-center mx-auto">
      <div class="c-work__head">
        <h2>WORK</h2>
        <div class="c-slider">
          <div class="c-slider__item justify-center flex items-center">
            <div class="c-desc w-2/5">
              <h3 class="c-desc__title">アンゴウメッセ</h3>
              <p class="c-desc__text">
                アンゴウメッセはVue.jsとFirebaseを使って作成した人生初のウェブアプリです。
                子供の頃に暗号を使って友達と会話してみたいという小さな夢を叶えるために作成したプロジェクトです。
              </p>
            </div>
            <div class="c-item w-3/5">
              <img
                src="@/assets/images/work/work1.png"
                alt=""
                class="c-item__img"
              />
            </div>
          </div>
          <div class="c-slider__left">
            <a href="#" class="c-slider__cursor">
              <img
                class="c-slider__icon"
                src="@/assets/images/work/arrow_left.svg"
                alt=""
              />
            </a>
          </div>
          <div class="c-slider__right">
            <a href="" class="c-slider__cursor">
              <img
                class="c-slider__icon"
                src="@/assets/images/work/arrow_right.svg"
                alt=""
              />
            </a>
          </div>
        </div>
        <div class="c-buttons mt-24">
          <a href="" class="c-buttons__buttonm border px-8 py-2 inline-block">
            see more
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: {}
}
</script>

<style lang="scss" scoped>
.c-work {
  padding: 240px 0;
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

  &__cursor {
    display: inline-block;
    border: 1px solid #fff;
    border-radius: 50%;
    line-height: 0.8;
    width: 70px;
    height: 70px;
    line-height: 70px;
    font-size: 40px;

    &:hover {
      background-color: #fff;
    }
  }

  &__icon {
    width: 30px;
    height: 70px;
    margin: 0 auto;
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
}

.c-desc {
  margin-right: 40px;
  text-align: left;
  max-width: 320px;
  &__title {
    font-size: 24px;
    font-weight: bold;
  }

  &__text {
    margin-top: 8px;
    font-size: 16px;
    line-height: 2;
  }
}
</style>
