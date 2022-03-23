<template>
  <div class="container">
    <h1 class="text-center">Priority List</h1>

    <!-- Input Box: -->
    <div class="d-flex">
      <input
        v-model="taskInputValue"
        type="text"
        placeholder="Write a T Do ..."
        class="form-control rounded-left"
      />

      <!-- Checkbox: -->
      <div class="d-flex">
        <div>
          <input
            type="checkbox"
            id="important"
            name="important"
            value="important"
            v-model="importantPriority"
          />
          <label for="important">Important</label>
        </div>

        <div>
          <input
            type="checkbox"
            id="urgent"
            name="urgent"
            value="urgent"
            v-model="urgentPriority"
          />
          <label for="urgent">Urgent</label>
        </div>
      </div>

      <button @click="addPriority" class="btn btn-success rounded-right">
        Add
      </button>
    </div>

    <!-- Priority List: -->
    <div id="tables">
      <table class="table table-bordered mt-5">
        <thead>
          <tr>
            <th>Task Name</th>
            <th>Status</th>
            <th colspan="2" style="text-align: center">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr class="bg-success">
            <td colspan="4">Highest Priority</td>
          </tr>
          <tr
            v-for="(task, index) in tasks.filter((task) => task.importantPriority === true && task.urgentPriority == true)"
            :key="index"
          >
            <td>
              <span :class=" {'finished' : task.status === 'done'} ">{{ task.name }}</span>
            </td>
            <td style="width: 120px">
              <span  @click="changeStatus(index)" class="pointer">{{ firtCharUpper(task.status) }}</span>
            </td>
            <td class="text-center">
              <div @click="editTask(task)">
                <i class="fa-solid fa-pen"></i>
              </div>
            </td>
            <td class="text-center">
              <div>
                <i class="fa-solid fa-trash"></i>
              </div>
            </td>
          </tr>
          <tr class="bg-warning">
            <td colspan="4">Medium Priority</td>
          </tr>
           <!-- <tr
            v-for="(task, index) in tasks.filter((task) => task.priority === 'ni')"
            :key="index"
          > -->
          <tr
            v-for="(task, index) in tasks.filter((task) => task.importantPriority === true && task.urgentPriority == false)"
            :key="index"
          >
            <td>
              <span :class=" {'finished' : task.status === 'done'} ">{{ task.name }}</span>
            </td>
            <td style="width: 120px">
              <span @click="changeStatus(index)" class="pointer">{{ firtCharUpper(task.status) }}</span>
            </td>
            <td class="text-center">
              <div @click="editTask(task)">
                <i class="fa-solid fa-pen"></i>
              </div>
            </td>
            <td class="text-center">
              <div>
                <i class="fa-solid fa-trash"></i>
              </div>
            </td>
          </tr>
          <tr class="bg-primary">
            <td colspan="4">Lowest Priority</td>
          </tr>
          <tr
            v-for="(task, index) in tasks.filter((task) => task.importantPriority === false && task.urgentPriority == true)"
            :key="index"
          >
            <td>
              <span :class=" {'finished' : task.status === 'done'} ">{{ task.name }}</span>
            </td>
            <td style="width: 120px">
              <span @click="changeStatus(index)" class="pointer">{{ firtCharUpper(task.status) }}</span>
            </td>
            <td class="text-center">
              <div @click="editTask(task)">
                <i class="fa-solid fa-pen"></i>
              </div>
            </td>
            <td class="text-center">
              <div>
                <i class="fa-solid fa-trash"></i>
              </div>
            </td>
          </tr>
          <tr class="bg-danger">
            <td colspan="4">Eliminated</td>
          </tr>
          <tr
            v-for="(task, index) in tasks.filter((task) => task.importantPriority === false && task.urgentPriority === false)"
            :key="index"
          >
            <td>
              <span :class=" {'finished' : task.status === 'done'} ">{{ task.name }}</span>
            </td>
            <td style="width: 120px">
              <span @click="changeStatus(index)" class="pointer">{{ firtCharUpper(task.status) }}</span>
            </td>
             <td class="text-center">
              <div @click="editTask(task)">
                <i class="fa-solid fa-pen"></i>
              </div>
            </td>
            <td class="text-center">
              <div>
                <i class="fa-solid fa-trash"></i>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "PriotitiesApp",
  props: {
    msg: String,
  },

  data() {
    return {
      taskInputValue: "",
      taskEditedInputValue: null,
      allStatuses: ["to-do", "in-progress", "done"],
      importantPriority: false,
      urgentPriority: true,
      tasks: [
        {
          name: "Hammmaaaash Aieno Bemalam",
          status: "To-do",
          importantPriority: true,
          urgentPriority: true,
        },
        {
          name: "Learn English",
          status: "To-do",
          importantPriority: true,
          urgentPriority: true,
        },
        {
          name: "Learn Vue.js",
          status: "To-do",
          importantPriority: false,
          urgentPriority: true,
        },
        {
          name: "Lebas bepusham vase Aien",
          status: "To-do",
          importantPriority: true,
          urgentPriority: false,              
        },
        {
          name: "Ba Aien Beshinam Bazi konam",
          status: "To-do",
          importantPriority: false,
          urgentPriority: false,
        },
      ],
    };
  },

  methods: {
    addPriority() {
      if (this.taskInputValue.length === 0) return;

      if (this.taskEditedInputValue === null) {
      this.tasks.push({
        name: this.taskInputValue,
        status: "To-do",
        importantPriority: this.importantPriority,
        urgentPriority: this.urgentPriority,
      });
      /* console.log(this.taskInputValue);
      console.log(this.importantPriority);
      console.log(this.tasks); */
      } else {
        this.tasks[this.taskEditedInputValue].name = this.taskInputValue;
        this.taskEditedInputValue = null;
      }
      this.taskInputValue = "";
      this.importantPriority = "";
      this.urgentPriority = "";
    },

    editTask(task) {
      this.taskInputValue = task.name;
      this.taskEditedInputValue = this.tasks.indexOf(task);
    },

    changeStatus(index) {
      let newIndex = this.allStatuses.indexOf(this.tasks[index].status);
      newIndex += 1;
      if(newIndex > 2) newIndex = 0;
      this.tasks[index].status = this.allStatuses[newIndex];
    },

    firtCharUpper(string) {
      return string.charAt(0).toUpperCase() + string.slice(1);
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
