<template>
  <TrafficSign
    class="lights__red circle"
    :svg="svg"
    v-bind:colorActive="colorActive"
  />
</template>

<script>
import TrafficSign from "@/components/TrafficSign/TrafficSign";
export default {
  props: ["svg", "colorActive"],
  components: {
    TrafficSign,
  },
};
</script>
