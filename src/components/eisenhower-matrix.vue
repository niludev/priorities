<template>
  <div>
    <h3 class="mt-5">Eisenhower Matrix</h3>


    <div class="matrix">
      <div class="matrix-item1">
        <p class="text-center">urgent</p>
      </div>
      <div class="matrix-item2">
        <p class="text-center">not urgent</p>
      </div>
      <div class="matrix-item3">
        <p style="text-align: center; writing-mode: vertical-rl; transform: rotate(180deg);">Important</p>
      </div>
      <div class="matrix-item4">
        <p style="text-align: center; writing-mode: vertical-rl; transform: rotate(180deg);">Not important</p>
      </div>
      <div class="matrix-item5">
        <div class="p-3 border bg-success">Do First (now)</div>
      </div>
      <div class="matrix-item6">
        <div class="p-3 border bg-warning">Do Later (schedule)</div>
      </div>
      <div class="matrix-item7">
        <div class="p-3 border bg-primary">Delegate (sombody)</div>
      </div>
      <div class="matrix-item8">
        <div class="p-3 border bg-danger">Don't Do (Eliminate)</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EisenhowerMatrix",
  props: {
    msg: String,
  },
};
</script>


<style scoped>
</style>
