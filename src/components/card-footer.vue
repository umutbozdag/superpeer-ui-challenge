<template>
  <footer class="call-footer row justify-center">
    <super-button variant="primary" aria-label="Join Call">
      <span class="size-normal">Join Call</span>
    </super-button>
  </footer>
</template>

<script>
import SuperButton from "./super-button";
export default {
  name: "CardFooter",
  components: {
    SuperButton
  }
};
</script>

<style lang="scss" scoped>
.call-footer {
  border: none;
}
</style>
