<template>
  <!-- :key ? -->
  <div :key="task.id" v-for="task in tasks">
    <!-- // emit will transfer this to next level up to App.vue -->
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)"
      :task="task" />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "edit-task", "toggle-reminder"],
};
</script>
