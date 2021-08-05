<template>
  <div class="lights">
    <div class="lights__wrapper">
      <div class="lights__green circle">
        <img class="lights__green-img" :src="lightWalk" alt="walking" />
      </div>
      <div class="lights__yellow circle">
        <img class="lights__yellow-img" :src="lightStanding" alt="standing" />
      </div>
      <div class="lights__red circle">
        <img class="lights__red-img" :src="lightStop" alt="stop" />
      </div>
    </div>
    <div class="lights__stick"></div>
  </div>
</template>

<script>
import lightWalk from "@/assets/lights-walk.svg";
import lightStanding from "@/assets/lights-standing.svg";
import lightStop from "@/assets/lights-stop.svg";

export default {
  name: "TraficLights",
  props: {},
  setup() {
    return {
      lightWalk,
      lightStanding,
      lightStop,
    };
  },
};
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
@import "./TraficLights.module.scss";
</style>
