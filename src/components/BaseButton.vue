<template>
  <button @click="$emit('click')" :style="buttonStyle" :class="buttonClasses">
    Click
    <img class="base-button__icon" src="https://picsum.photos/30" alt="">
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    buttonType: {
      type: String,
      default: "primary",
    },
    fontSize: {
      type: Number,
      default: 1.5,
    },
  },
  computed: {
    buttonClasses() {
      return [
        "base-button",
        { "base-button--primary": this.buttonType === "primary" },
        { "base-button--secondary": this.buttonType === "secondary" },
        { "base-button--tertiary": this.buttonType === "tertiary" },
      ];
    },
    buttonStyle() {
      return `font-size: ${this.fontSize}rem`;
    },
  },
};
</script>

<style lang="scss" scoped>
.base-button {
  display: block;
  padding: 0.5em 1em;
  border: 0;
  border-radius: 0.5rem;
  transition: background-color 0.2s;

  &:hover {
    background-color: darken($color-primary, 5%);
  }

  &--primary {
    background: $color-primary;
    color: white;
  }

  &--secondary {
    color: white;
    background: $color-secondary;
  }

  &--tertiary {
    background: transparent;
    border: 2px solid $color-primary;
  }
}
</style>