<template>
  <li class="video-control-item">
    <abbr :title="controlItem.label">
      <super-button
        class="video-control-btn"
        variant="secondary"
        rounded
        :aria-haspopup="controlItem.id === 2"
        width="48px"
        :aria-label="controlItem.label"
      >
        <i :class="`icon ${controlItem.icon}`" role="img"></i>
      </super-button>
    </abbr>
  </li>
</template>

<script>
import SuperButton from "./super-button";
export default {
  name: "VideoControlItem",
  components: {
    SuperButton
  },
  props: {
    controlItem: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../styles/variables";
.video-control-item {
  margin-right: 12px;

  &:last-child {
    margin-right: 0;
  }
  .video-control-btn {
    &:hover {
      background-color: $grey-40;
    }
    &:focus {
      background-color: $grey-40;
    }

    .icon {
      font-size: 20px;
      color: $icon-color;
    }
  }
}
</style>
