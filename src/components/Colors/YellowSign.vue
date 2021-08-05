<template>
  <TrafficSign
    class="lights__yellow circle"
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
