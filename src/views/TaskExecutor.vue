<template>
    <div>
        <h2>Исполнитель задачи</h2>
        <select name='options'  v-model ="taskExecutor" class="task-executor">
            <option value='Иванов'>Иванов
            </option>
            <option value='Петров'>Петров
            </option>
            <option value='Сидоров'>Сидоров
            </option>
             <option value='Акопян'>Акопян
            </option>
        </select>
        <router-link to="/time" class="button">Назад
        </router-link>
        <router-link to="/list" @click = "createTaskExecutor" class="button"
         :class="{ disabled: !taskExecutor.length }">Завершить создание задачи
        </router-link>
    </div>
</template>
<script>
export default {
      data: function () {
    return {
      taskExecutor: ""
    }
  },
  methods: {
    createTaskExecutor: function () {
      // this.nameValue = this.taskName
      this.$emit('createTaskExecutor', this.taskExecutor);
    }

  },
 emits: ['createTaskExecutor'],

}
</script>

<style>
.task-executor {
  display: block;
  margin: 0 auto;
  width: 180px;
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