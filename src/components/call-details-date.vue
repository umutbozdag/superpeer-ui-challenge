<template>
  <section class="call-date-and-time">
    <div id="call-time-info" class="call-time-info row justify-center brd-8" aria-readonly="true">
      <div class="call-date row mr-24">
        <!-- Reference: https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA24.html -->
        <i
          role="img"
          aria-describedby="call-date"
          aria-label="Call date"
          class="icon icon-calendar mr-8 text-primary"
        ></i>
        <time
          id="call-date"
          class="size-small text-grey-90"
          datetime="2020-10-07"
          aria-label="7 October, Wednesday,"
        >7 Oct, Weds</time>
      </div>

      <div class="call-time row">
        <i
          role="img"
          aria-label="Call time"
          aria-describedby="call-time"
          class="icon icon-clock mr-8 text-primary"
        ></i>
        <time
          id="call-time"
          class="size-small text-grey-90"
          datetime="10:15 - 10:30"
          aria-label="10:15AM - 10:30AM,"
        >10:15AM - 10:30AM</time>
      </div>
    </div>

    <p
      class="call-timezone text-center text-grey-80 mt-8 mb-24 size-small w-regular"
    >Timezone: Europe/Amsterdam</p>
  </section>
</template>

<script>
export default {
  name: "CallDetailsDate"
};
</script>

<style lang="scss" scoped>
@import "../styles/main";

.call-date-and-time {
  .call-time-info {
    border: 1px solid $grey-40;
    margin: 0 16px;
    padding: 16px;
    height: 16px;
    line-height: 1.5;
  }
}
</style>

