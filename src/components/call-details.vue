<template>
  <section class="call-details">
    <call-details-header/>

    <call-details-date/>
  </section>
</template>

<script>
import CallDetailsHeader from "./call-details-header";
import CallDetailsDate from "./call-details-date";

export default {
  name: "CallDetails",
  components: {
    CallDetailsHeader,
    CallDetailsDate
  }
};
</script>
