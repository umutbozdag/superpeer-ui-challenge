<template>
  <select
    class="super-dropdown brd-8 size-normal"
    :id="id"
    :class="{disabled}"
    :name="name"
    :aria-disabled="disabled ? 'true' : 'false'"
    :required="required"
    :aria-required="required ? 'true' : 'false'"
    :disabled="disabled"
  >
    <slot></slot>
  </select>
</template>

<script>
export default {
  name: "SuperDropdown",
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String
    },
    required: {
      type: Boolean
    },
    disabled: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../styles/main";
.super-dropdown {
  @include super-dropdown;
  @include font-family;
  margin-left: -1px;
  flex: 2;

  &:focus {
    @include shadow;
  }

  &.disabled {
    background-color: $grey-40;
    cursor: not-allowed;
    &:focus {
      box-shadow: none;
    }
  }
}
</style>
