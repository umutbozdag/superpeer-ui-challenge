<template>
  <section id="card" class="initializing-card brd-16">
    <call-details/>
    <video-preview/>
    <setting-controls/>
    <card-footer/>
  </section>
</template>

<script>
import CallDetails from "./call-details";
import VideoPreview from "./video-preview";
import SettingControls from "./setting-controls";
import CardFooter from "./card-footer";

export default {
  name: "InitializingCard",
  components: {
    CallDetails,
    VideoPreview,
    SettingControls,
    CardFooter
  }
};
</script>

<style lang="scss">
@import "../styles/variables";
.initializing-card {
  max-width: 384px;
  padding: 32px 24px;
  background: $white;
  box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.1);
}
</style>

