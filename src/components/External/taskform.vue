<template>
  <div>
    <ul class="list-group">
      <Task
        v-for="t in tasks"
        v-bind:task="t"
        v-bind:key="t.id"
        v-on:on-delete-task="deleteTask"
        v-on:on-task-edited="editTask"
      />
    </ul>
    <h2>Add New Task</h2>
    <TaskForm
      v-on:new-task-added="addTask"
      mode="adding"
      v-bind:initialTask="{
        name: '',
        urgency: 1,
        importance: 1,
        date: new Date(),
      }"
    />
  </div>
</template>

<script>
import Task from "@/components/Task";
import TaskForm from "@/components/TaskForm";

export default {
  data: function () {
    return {
      newTask: {
        name: "",
        ugency: "",
        importance: "",
        dateDue: "",
      },

      tasks: [
        {
          id: 1,
          name: "Wash the car",
          urgency: 5,
          importance: 2,
          dateDue: "2021-12-31",
        },
        {
          id: 2,
          name: "Pay income tax",
          urgency: 3,
          importance: 5,
          dateDue: "2022-04-15",
        },
        {
          id: 3,
          name: "Return library book",
          urgency: 2,
          importance: 2,
          dateDue: "2022-01-02",
        },
      ],
    };
  },
  components: { Task, TaskForm },
  methods: {
    addTask: function (newTask) {
      // create and assign an id manually to the newTask object
      newTask.id = Math.floor(Math.random() * 10000 + 9999);
      this.tasks.push(newTask);
    },
    deleteTask: function (taskToDelete) {
      // 1. find the index of task to delete
      //  ... find the index of task which id matches the id of the task that
      //      we want to delete
      let indexToDelete = this.tasks.findIndex((t) => t.id === taskToDelete.id);

      // alternatively to find the index of the task to delete:
      // let indexToDelete = -1;
      // for (let i =0; i < this.tasks.length; i++) {
      //   if (this.tasks[i].id === taskDToDelete.id) {
      //     indexToDelete = i;
      //     break;
      //   }
      // }

      // 2. remove the task from the tasks array
      this.tasks.splice(indexToDelete, 1);
    },
    editTask: function (taskToEdit) {
      let indexToEdit = this.tasks.findIndex((t) => t.id === taskToEdit.id);
      // reminder: we cannot use [] operator to change the content of
      // an array in vue
      //this.tasks[indexToEdit] = taskToEdit;
      this.$set(this.tasks, indexToEdit, taskToEdit);
    },
  },
};
</script>