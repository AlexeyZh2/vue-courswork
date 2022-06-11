<template>
  <div class="home">
    <h2>Название задачи</h2>
    <input type="text" v-model="taskName">
   <router-link to="/about"
      @click="createTaskName" class="button" 
      :class="{ disabled: !taskName.length }">Далее
    </router-link>
  </div>
  
</template>

<script>

export default {
  data: function () {
    return {
      taskName: "",
      disabled: true,
      errorActive: true,
    }
  },
  methods: {
    createTaskName: function () {
      this.$emit('createTaskName', this.taskName);
    },


  },
  
  emits: ['createTaskName'],


}

</script>
<style>
.button {
  text-decoration: none;
  border: 1px solid black;
  color: rgb(40, 32, 32);
  width: 150px;
  display: block;
  margin: 20px auto;
}

.err {
  display: none;
  margin-top: 0;
}

.err_active {
  display: block;
  color: red;
  margin-top: 0;
}
.disabled {
    opacity: 0.5;
    pointer-events: none;
}
</style>
