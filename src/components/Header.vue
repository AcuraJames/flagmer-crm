<template>
  <div class="header">
    <div class="header__logo">
      <img class="logo" src="@/assets/icons/logo.svg" />
      <span class="logo-text">Privacy Credits</span>
      <img class="chevron" src="@/assets/icons/chevron.svg" />
    </div>
    <div class="header__controls">
      <div class="control-icon"><img src="@/assets/icons/question.svg" /></div>
      <div class="control-icon"><img src="@/assets/icons/dots.svg" /></div>
      <div class="control-button" @click="$emit('showModal')">
        <img src="@/assets/icons/plus.svg" />
        <span>Создать заявку</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
@import '@/assets/css/base.scss';
.header {
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: space-between;
  background-color: #2a3247;
  color: #fff;

  &__logo,
  &__controls {
    display: flex;
    align-items: center;
  }

  &__logo {
    margin-left: 70px;
    font-size: 14px;

    @media (max-width: 992px) {
      margin-left: 20px;
    }

    .logo {
      margin-right: 5px;
    }
    .logo-text {
      @media (max-width: 480px) {
        display: none;
      }
    }

    .chevron {
      margin-left: 12px;
      cursor: pointer;
    }
  }

  &__controls {
    cursor: pointer;

    .control-icon {
      width: 50px;
      height: 40px;
      position: relative;
      border-left: 1px solid $primary;

      img {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin: auto;
      }
    }

    .control-button {
      width: 150px;
      height: 100%;
      padding: 15px;
      display: flex;
      align-items: center;
      background-color: $accent;
      box-sizing: border-box;

      &:hover {
        background-color: darken($accent, 10%);
      }

      @media (max-width: 480px) {
        width: 50px;
        justify-content: center;
      }

      span {
        margin-left: 8px;
        font-size: 14px;

        @media (max-width: 480px) {
          display: none;
        }
      }
    }
  }
}
</style>
