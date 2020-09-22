<template>
  <ul class="video-controls row justify-center">
    <video-control-item
      v-for="controlItem in videoControlItems"
      :key="controlItem.id"
      :control-item="controlItem"
    />
  </ul>
</template>

<script>
import VideoControlItem from "./video-control-item";

export default {
  components: {
    VideoControlItem
  },
  data() {
    return {
      videoControlItems: [
        {
          id: 0,
          icon: "icon-microphone",
          label: "Mute/Unmute Voice"
        },
        {
          id: 1,
          icon: "icon-camera",
          label: "Open/Close Camera"
        },
        {
          id: 2,
          icon: "icon-options",
          label: "Settings"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.video-controls {
  position: absolute;
  bottom: 12px;
  width: 100%;
}
.video-control-btn {
  img {
    width: 20px;
    height: 20px;
  }
}
</style>
