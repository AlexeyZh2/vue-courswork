<template>
  <nav>
    <router-link to="/task">Приступить к созданию
      задачи
     </router-link>
  </nav>
  
  <router-view @createTaskName="taskName"
    @createTaskAbout="taskAbout"
    @createTaskTime="taskTime"
    @createTaskExecutor = "taskExecutor" 
    :tasks = "tasksList"/>
</template>

<script>
//import tasksList from './views/TaskList'

export default {
 // components: [tasksList],
  data() {
    return {
      task: {
        id: 0,
        name: "",
        about: "",
        time: null,
        executor: ""
      },
      tasksList : []


    }
  },
  methods: {
    taskName(taskName) {
      this.task.name = taskName
  
    },
    taskAbout(aboutTask) {
      this.task.about = aboutTask
    },
    taskTime(taskTime) {
      this.task.time = taskTime
    },
     taskExecutor(taskExecutor) {
      this.task.executor = taskExecutor
      let fullTask = {
        id: this.task.id++,
        name: this.task.name,
        about: this.task.about,
        time: this.task.time,
        executor: this.task.executor
      }
      console.log(fullTask)
       this.tasksList.push(fullTask)
      console.log(this.tasksList)
    },
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
