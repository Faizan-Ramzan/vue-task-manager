<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" @update-task="$emit('update-task', task)" :task="task" />
    </div>
</template>

<script>
import Task from './task.vue'

    export default {
        name: 'Tasks',
        props: {
            tasks: Array,
        },
        components: {
            Task
        },
        emits: ['delete-task', 'toggle-reminder', 'update-task']
    }
</script>