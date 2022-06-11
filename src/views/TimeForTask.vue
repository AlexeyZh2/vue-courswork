<template>
<div>
    <h2>Время необходимое для выполнения задачи</h2>
    <input type ="number" v-model = "taskTime" class="task-time">
    <router-link to = "/about" class="button">Назад</router-link>
    <router-link to = "/executor" @click="createTaskTime" class="button"
     :class="{ disabled: !taskTime }">Далее</router-link>
</div>
</template>
<script>
export default {
     data: function () {
    return {
      taskTime: null
    }
  },
  methods: {
    createTaskTime: function () {
      this.$emit('createTaskTime', this.taskTime);
    }

  },
 emits: ['createTaskTime'],


}
</script>
<style>
.task-time {
  display: block;
  margin: 0 auto;
}
.button {
  border: 1px solid black;
  text-decoration: none;
  color: rgb(40, 32, 32);
  width: 150px;
  border-radius: 5px;
  display: inline-block;
  margin: 20px auto;
}
.disabled {
    opacity: 0.5;
    pointer-events: none;
}
</style>