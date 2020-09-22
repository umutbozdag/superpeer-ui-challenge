<template>
  <div class="super-input-wrapper row brd-8" role="search" :class="{disabled}">
    <slot name="icon"></slot>
    <input
      :value="value"
      :placeholder="placeholder"
      :name="name"
      :aria-placeholder="placeholder"
      :required="required"
      @input="$emit('input', $event.target.value)"
      :aria-required="required ? 'true' : 'false'"
      class="super-input brd-8 flex-1"
      :aria-label="placeholder"
      type="text"
      :disabled="disabled"
    >
  </div>
</template>

<script>
export default {
  name: "SuperInput",
  model: {
    prop: "value",
    event: "input"
  },
  props: {
    required: {
      type: String,
      default() {
        return false;
      }
    },
    value: {
      type: [String, Number],
      required: true
    },
    placeholder: {
      type: String
    },
    name: {
      type: String
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
.super-input-wrapper {
  border: 1px solid $grey-40;
  height: 48px;
  outline: 0;

  &:focus-within,
  &:active {
    @include shadow();
  }

  &.disabled {
    cursor: not-allowed;
    background-color: $grey-40;
    .icon {
      color: $grey-80 !important;
    }
    .super-input {
      color: $grey-80;
      background-color: $grey-40;
      cursor: not-allowed;
    }
    &:focus-within,
    &:active {
      @include shadow($none: true);
    }
  }
}
.super-input {
  @include super-input();
}

.icon-user {
  margin-left: 16px;
  margin-right: 6px;
}
</style>

