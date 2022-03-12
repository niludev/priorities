<template>
  <div id="app" class="m-3">
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css"
      integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg=="
      crossorigin="anonymous"
      referrerpolicy="no-referrer"
    />

    <div class="row g-5">
      <EisenhowerMatrix class="col-md-2"></EisenhowerMatrix>
      <PrioritiesApp class="col-md-8"></PrioritiesApp>
      <DescriptionApp class="col-md-2"></DescriptionApp>
    </div>
  </div>
</template>

<script>
import PrioritiesApp from "./components/priorities-app.vue";
import DescriptionApp from "./components/description-app.vue";
import EisenhowerMatrix from "./components/eisenhower-matrix.vue";

export default {
  name: "App",
  components: {
    PrioritiesApp,
    EisenhowerMatrix,
    DescriptionApp,
  },
};
</script>

<style>
</style>
