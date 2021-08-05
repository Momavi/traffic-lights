<template>
  <div v-bind:class="{ active: colorActive === true }">
    <img :src="svg" alt="sign" />
  </div>
</template>

<script>
export default {
  props: ["svg", "colorActive"],
};
</script>
