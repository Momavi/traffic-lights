<template>
  <div class="lights">
    <div class="lights__wrapper">
      <GreenSign
        :svg="signWalk"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[0].id"
      />
      <YellowSign
        :svg="signStanding"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[1].id"
      />
      <RedSign
        :svg="signStop"
        v-bind:signActiveId="signActiveId"
        v-bind:activeId="signs[2].id"
      />
    </div>
    <div class="lights__stick"></div>
    <button @click="nextSign">Жми</button>
  </div>
</template>

<script>
import signWalk from "@/assets/sign-walk.svg";
import signStanding from "@/assets/sign-standing.svg";
import signStop from "@/assets/sign-stop.svg";

import GreenSign from "@/components/Colors/GreenSign.vue";
import YellowSign from "@/components/Colors/YellowSign.vue";
import RedSign from "@/components/Colors/RedSign.vue";

export default {
  props: ["signs"],
  data() {
    return {
      signActiveId: this.searchActiveSign(),
    };
  },
  setup() {
    return {
      signWalk,
      signStanding,
      signStop,
    };
  },
  components: {
    GreenSign,
    YellowSign,
    RedSign,
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
@import "./TrafficLights.module.scss";
</style>
