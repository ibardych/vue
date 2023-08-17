<template>
  <div class="container">
    <Header title="Tasks" />
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header';
import Tasks from './components/Tasks';

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  // data() {
  //   return {
  //     tasks
  //   }
  // },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Lorem ipsum",
        day: 'date 1',
        reminder: true,
      },
      {
        id: 2,
        text: "Dolor set",
        day: 'date 2',
        reminder: false,
      },
      {
        id: 3,
        text: "Consetetur sadipscing",
        day: 'date 3',
        reminder: true,
      },
    ]
  },
  methods: {
    deleteTask(id) {
      console.log(id);
    }
  }
}
</script>

<style>
body {
  background-color: #333;
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
