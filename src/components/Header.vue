<template>
  <header>
    <h1>{{title}}</h1>
    <Button v-show="homePage" @toggle-add-task="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? '#b80946' : '#67d500'" />
  </header>
</template>

<script>
import Button from './Button';

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if(this.$route.path === "/") {
        return true;
      }else {
        return false;
      }
    }
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