<template>
  <div class="container">
    <h1 class="text-center">Priority List</h1>

    <!-- Input Box: -->
    <div class="d-flex">
      <input placeholder="Write a T Do ..." class="form-control rounded-left" />

      <!-- Checkbox: -->
      <div class="d-flex">
        <div>
          <input type="checkbox" id="important" name="important" />
          <label for="important">Important</label>
        </div>

        <div>
          <input type="checkbox" id="urgrnt" name="urgrnt" />
          <label for="urgrnt">Urgent</label>
        </div>
      </div>

      <button class="btn btn-success rounded-right">Add</button>
    </div>

    <!-- Priority List: -->
    <div id="tables">
      <table class="table table-bordered mt-5">
        <div id="1-highPriority">
          <thead>
            <tr class="bg-success">
              <th scope="col" class="w-75">High Priority</th>
              <th scope="col">Status</th>
              <th scope="col" class="text-center">Edit</th>
              <th scope="col" class="text-center">Delete</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <span>Learn English</span>
              </td>
              <td style="width: 120px">
                <span>To-do</span>
              </td>
              <td class="text-center">
                <div>
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
        </div>

        <div id="2-mediumPriority">
          <thead>
            <tr class="bg-warning">
              <th scope="col" class="w-75">Medium Priority</th>
              <th scope="col">Status</th>
              <th scope="col" class="text-center">Edit</th>
              <th scope="col" class="text-center">Delete</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <span>Learn Vue.js</span>
              </td>
              <td style="width: 120px">
                <span>To-do</span>
              </td>
              <td class="text-center">
                <div>
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
        </div>

        <div id="3-lowPriority">
          <thead>
            <tr class="bg-primary">
              <th scope="col" class="w-75">Low Priority</th>
              <th scope="col">Status</th>
              <th scope="col" class="text-center">Edit</th>
              <th scope="col" class="text-center">Delete</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <span>Learn Vue.js</span>
              </td>
              <td style="width: 120px">
                <span>To-do</span>
              </td>
              <td class="text-center">
                <div>
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
        </div>

        <div id="4-eliminate">
          <thead>
            <tr class="bg-danger">
              <th scope="col" colspan="4" class="w-75">Eliminate</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td colspan="4">Checking Instagram</td>
            </tr>
          </tbody>
        </div>

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
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
