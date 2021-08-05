<template>
  <TraficLights v-bind:signs="signs" />
</template>

<script>
import TraficLights from "./components/TraficLights.vue";

export default {
  components: {
    TraficLights,
  },
  data() {
    return {
      signs: [
        { id: 1, color: "green", active: true, timer: 15 },
        { id: 2, color: "yellow", active: false, timer: 3 },
        { id: 3, color: "red", active: false, timer: 10 },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
