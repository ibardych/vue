<template>
  <div class="tasks">
    <template  :key="task.id" v-for="task in tasks">
      <Task @delete-task="$emit('delete-task', task.id)" :task="task" />
    </template>
  </div>
</template>

<script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  props: {
    tasks: Array
  },
  components: {
    Task
  }
}
</script>

<style>
  .tasks {
    display: flex;
    gap: 10px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: 20px;
  }
</style>