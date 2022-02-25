<template>
  <div class="app">
    <div class="app__container">
      <p class="app__description">
        IJFSISAF asififsaisa asijfifsa iasasf saifhsafsaifsa
      </p>
      <div class="app__button-wrapper">
        <BaseButton />
        <BaseButton buttonType="secondary" :fontSize="1" />
        <BaseButton buttonType="tertiary" :fontSize="2" />
      </div>

      <BaseButton class="wide" />

      <h2 class="app__heading">
        CLAMP
      </h2>

      <!-- <div class="app__squares">
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
        <div class="app__square" />
      </div> -->
    </div>
  </div>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";
export default {
  name: "App",
  components: {
    BaseButton,
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/global/index.scss";
.app {
  &__container {
    background: #ddd;
    width: min(100%, 800px);
    padding: 2rem;
    margin: 0 auto;
  }

  &__button-wrapper {
    display: flex;

    .base-button {
      margin-right: 0.5rem;

      &:last-of-type {
        margin: 0 auto;
      }

      &:first-of-type {
        margin-right: auto;
      }
    }
  }

  ::v-deep .base-button__icon {
    width: 50px;
  }

  .wide {
    width: calc(100% - 2rem);
  }

  &__squares {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  &__square {
    background: blue;
    width: calc((100% - 2 * 1rem) / 3);
    height: 100px;
    margin-bottom: 1rem;
  }

  &__heading {
    font-size: clamp(1rem, 2vw + 0.5rem, 2rem);

    @include rwd(1300px) {
      /* color: green; */
    }

    @include hover-darken(orangered);
  }
}
</style>
