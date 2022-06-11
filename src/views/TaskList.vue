<template>
    <div>
        <h2>Список задач</h2>
        <div v-for="task in tasks" :key="task.id"
            class="task-item">
            <h3>Название задачи: {{ task.name }}
            </h3>
            <p>Описание задачи: {{ task.about }}</p>
            <p>Необходимое время: {{ task.time }}
                часов</p>
            <p>Исполнитель : {{ task.executor }}
            </p>
        </div>
        <!-- <router-view></router-view> -->
        <router-link to="/task">Создать новую
            задачу</router-link>
    </div>
</template>
 
<script>
export default {
    props: {
        tasks: Array
    }

}
</script>
<style>
.task-item {
    margin:0 auto 15px;
    width: 60%;
    text-align: left;
    background-color: lightskyblue;

}
</style>