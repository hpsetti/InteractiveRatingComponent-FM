<template>
  <div class="app d-flex justify-center align-items-center">
    <InteractiveRating />
  </div>
</template>

<script>
import InteractiveRating from "@/components/InteractiveRating.vue";
export default {
  name: "App",
  components: {
    InteractiveRating,
  },
};
</script>

<style>
.app {
  height: 100%;
  width: 100%;
}
</style>
