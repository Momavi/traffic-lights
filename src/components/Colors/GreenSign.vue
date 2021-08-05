<template>
  <TrafficSign
    class="lights__green circle"
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
