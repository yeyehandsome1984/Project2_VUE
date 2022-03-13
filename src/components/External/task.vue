<template>
  <li class="list-group-item">
    <!-- t is the variable that stores the task object -->
    <TaskForm
      v-if="isEditing"
      v-bind:initialTask="task"
      mode="editing"
      v-on:edit-task="onEditTask"
    />
    <div v-else>
      <h2>{{ task.name }}</h2>
      <ul>
        <li>Urgency: {{ task.urgency }}</li>
        <li>Importance: {{ task.importance }}</li>
        <li>Date Due: {{ task.dateDue }}</li>
      </ul>
      <button class="btn btn-sm btn-primary mx-1" v-on:click="onEditPressed">
        Edit
      </button>
      <button class="btn btn-sm btn-danger mx-1" v-on:click="onDeletePressed">
        Delete
      </button>
      <button class="btn btn-sm btn-success mx-1">Mark as done</button>
    </div>
  </li>
</template>

<script>
import TaskForm from "@/components/TaskForm";
export default {
  props: ["task"],
  methods: {
    onDeletePressed: function () {
      this.$emit("on-delete-task", this.task);
    },
    onEditPressed: function () {
      this.isEditing = true;
    },
    onEditTask: function (taskBeingEdited) {
      this.isEditing = false;
      // assign the id of the current task to the
      // new edited task
      taskBeingEdited.id = this.task.id;
      this.$emit("on-task-edited", taskBeingEdited);
    },
  },
  data: function () {
    return {
      isEditing: false,
    };
  },
  components: {
    TaskForm,
  },
};
</script>