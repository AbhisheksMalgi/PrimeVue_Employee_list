<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @toggle-active="$emit('toggle-active', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
    </div>
</template>

<script>
import Task from './Task.vue';
export default {
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        Task,
    },
    emit: ['delete-task', 'toggle-active'],
}
</script>

<style>
.task {
    background-color: aliceblue;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
</style>