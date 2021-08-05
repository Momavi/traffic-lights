<template>
  <div class="lights">
    <div class="lights__wrapper">
      <TraficItem
        class="lights__green circle"
        :svg="lightWalk"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[0].id"
      />
      <TraficItem
        class="lights__yellow circle"
        :svg="lightStanding"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[1].id"
      />
      <TraficItem
        class="lights__red circle"
        :svg="lightStop"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[2].id"
      />
    </div>
    <div class="lights__stick"></div>
    <button @click="nextSign">Жми</button>
  </div>
</template>

<script>
import lightWalk from "@/assets/lights-walk.svg";
import lightStanding from "@/assets/lights-standing.svg";
import lightStop from "@/assets/lights-stop.svg";

import TraficItem from "@/components/TraficItem/TraficItem";

export default {
  props: ["signs"],
  data() {
    return {
      signActiveId: this.searchActiveSign(),
    };
  },
  setup() {
    return {
      lightWalk,
      lightStanding,
      lightStop,
    };
  },
  components: {
    TraficItem,
  },
  methods: {
    nextSign() {
      if (this.signActiveId > 2) this.signActiveId = 0;
      this.signActiveId++;
    },
    searchActiveSign() {
      let activeSign = "";
      for (var i = 0; i < this.signs.length; i++) {
        if (this.signs[i].active) {
          activeSign = this.signs[i].id;
        }
      }
      return activeSign;
    },
  },
};
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
@import "./TraficLights.module.scss";
</style>
