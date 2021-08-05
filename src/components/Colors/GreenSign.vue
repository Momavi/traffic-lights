<template>
  <TrafficSign
    class="lights__green circle"
    :svg="svg"
    v-bind:signActiveId="signActiveId"
    v-bind:activeId="activeId"
  />
</template>

<script>
import TrafficSign from "@/components/TrafficSign/TrafficSign";
export default {
  props: ["svg", "signActiveId", "activeId"],
  components: {
    TrafficSign,
  },
};
</script>
