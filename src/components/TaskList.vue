<template>
    <div id="task-list" :key="task.name" v-for="task in tasks">
        <Task :task="task" />
    </div>
</template>

<script>
import Task from "./Task.vue";

export default {
    name: "TaskList",
    props: {
        tasks: Array,
    },
    components: {
        Task,
    }
}
</script>

<style scoped>
div {
    text-align: center;
    margin-left: 30%;
    margin-right: 3%;
}
</style>