<template>
  <div v-bind:class="{ active: signActiveId == activeId }">
    <img :src="svg" alt="sign" />
  </div>
</template>

<script>
export default {
  props: ["svg", "signActiveId", "activeId"],
};
</script>
