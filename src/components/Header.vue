<template>
  <header>
    <h1>{{title}}</h1>
    <Button @toggle-add-task="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? '#b80946' : '#67d500'" />
  </header>
</template>

<script>
import Button from './Button';

export default {
  name: "Header",
  components: {
    Button
  },
  props: {
    title: String,
    showAddTask: Boolean,
  }
}
</script>

<style scoped lang="scss">
  header {
    padding: 30px 0;
    background-color: rgba(255,255,255,0.1);
    
    & h1 {
      font-size: 18x;
      color: #f5f5f5;
    }
  }
</style>