<template>
  <Sidebar @add-task="addTask"/>
  <Header :counter="tasks.length"/>
  <TaskList :tasks="tasks"/>
</template>

<script>
import Header from "./components/Header.vue";
import TaskList from "./components/TaskList.vue";
import Sidebar from "./components/Sidebar.vue";

export default {
  name: 'App',
  components: {
    Header,
    TaskList,
    Sidebar,
  },
  data() {
    return {
      tasks: [],
      timers: [],
      completedTasks: [],
    }
  },
  methods: {
    addTask(task) {
      this.tasks = [...this.tasks, task];
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
  body {
    background-color: #262421;
    color: rgb(200,200,200);
    font-family: 'Poppins', sans-serif;
}
</style>
