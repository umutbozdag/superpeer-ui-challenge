<template>
  <button
    class="super-button size-normal brd-8"
    :style="{width, height}"
    :class="{'primary': variant === 'primary', 'secondary': variant === 'secondary', 
             rounded, outlined, disabled}"
    :aria-disabled="disabled ? 'true' : 'false'"
    @click="$emit('clicked')"
    :disabled="disabled"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "SuperButton",
  props: {
    variant: {
      type: String,
      validator(value) {
        return ["primary", "secondary"].indexOf(value) !== -1;
      }
    },
    outlined: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    rounded: {
      type: Boolean,
      default: false
    },
    width: {
      type: String,
      default: "100%"
    },
    height: {
      type: String,
      default: "48px"
    }
  }
};
</script>

<style scoped lang="scss">
@import "../styles/main";

.super-button {
  &.primary {
    @include super-button($primary, $white);

    &:hover {
      background-color: darken($primary, 5%);
    }

    &:focus,
    &:active {
      @include shadow();
    }
  }

  &.secondary {
    @include super-button($grey-10, $white, true);

    
    &:focus,
    &:hover {
      background-color: $grey-40;
      color: $white;
    }
    &:active {
      background-color: $primary;
      .icon {
        color: $white;
      }
    }

    &:active,
    &:focus {
      @include shadow(false, 0 0 0 0.15rem, darken($white, 2%));
    }
  }

  &.outlined {
    @include super-button($white, $primary, false, $border: 1px solid $primary);

    &:hover {
      background-color: darken($primary, 5%) !important;
      color: $white;
    }

    &:focus {
      background-color: $primary !important;
      color: $white;
      @include shadow;
    }
  }

  &.disabled {
    @include super-button($grey-40, $grey-80, false);

    cursor: not-allowed;

    &:focus, &:hover, &:active {
      box-shadow: none;
      color: $grey-80;
      background-color: $grey-40!important;
    }
  }

  &.rounded {
    @include brd-rounded();
  }
}
</style>


