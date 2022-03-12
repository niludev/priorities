<template>
  <div>
    <h3 class="mt-5">Eisenhower Matrix</h3>

    <div>
      <div class="row g-2">
        <div class="col-6 ">
          <p class="text-center">urgent</p>
          <div class="p-3 border bg-success">Do First (now)</div>
        </div>
        <div class="col-6">
          <p class="text-center">not urgent</p>
          <div class="p-3 border bg-warning">Do Later (schedule)</div>
        </div>
        <div class="col-6">
          <div class="p-3 border bg-primary">Delegate (sombody)</div>
        </div>
        <div class="col-6">
          <div class="p-3 border bg-danger">Don't Do (Eliminate)</div>
        </div>
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

  data() {
    return {
      todoInputValue: "",
      todoEditedInputValue: null,
      allStatuses: ["to-do", "in-progress", "done"],
      todos: [
        {
          name: "Learn English",
          status: "to-do",
        },
        {
          name: "Learn Vue.JS",
          status: "in-progress",
        },
      ],
    };
  },

  methods: {},
};
</script>


<style scoped>
</style>
