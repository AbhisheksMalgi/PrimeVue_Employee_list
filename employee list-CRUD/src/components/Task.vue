<template>
    <div @dblclick="$emit('toggle-active', task.id)" :class="[task.active ? 'active' : '', 'task']">
        <h3>{{ task.firstName }}
            <i @click="$emit('delete-task', task.id)" class="pi pi-times"></i>
        </h3>
        <p>{{ task.lastName }}</p>
        <p>{{ task.department }}</p>
        <p>{{ task.info }}</p>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: 'object',
    },
    methods: {
        onDelete(id) {
            this.emit('delete -task', id)
        }
    }
}
</script>

<style scoped>
.pi {
    color: red;
}

.task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}

.task.active {
    border-left: 5px solid green;
}

.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>