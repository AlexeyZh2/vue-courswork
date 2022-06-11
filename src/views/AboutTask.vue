<template>
<div>
    <h2>Описание задачи</h2>
    <textarea v-model = "aboutTask"></textarea>
    <router-link to = "/task" class="button">Назад</router-link>
    <router-link to = "/time" @click="createTaskAbout" class="button"
     :class="{ disabled: !aboutTask.length }">Далее</router-link>
</div>
</template>
<script>
export default {
     data: function () {
    return {
      aboutTask: ""
    }
  },
  methods: {
    createTaskAbout: function () {
      // this.nameValue = this.taskName
      this.$emit('createTaskAbout', this.aboutTask);
    }

  },
 emits: ['createTaskAbout'],

}


</script>
<style>
.button {
  border: 1px solid black;
  text-decoration: none;
  color: rgb(40, 32, 32);
  width: 150px;
  border-radius: 5px;
  display: inline-block;
  margin: 0 auto;
}
.disabled {
    opacity: 0.5;
    pointer-events: none;
}
</style>