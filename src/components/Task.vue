<template>
    <div class="item">
        <h2>{{task.name}}</h2>
        <h3>Posted just now</h3>
        <p>{{task.description}}</p>
        <button class="complete" type="button">Complete Task</button>
    </div>
</template>

<script>
export default {
    name: "Task",
    props: {
        task: Object,
    }
}
</script>


<style scoped>
div.item {
    background-color: #4d4d4d;
    padding: 5px;
    margin: 5px 0px 5px 0px;
}
button.complete {
    background-color: rgb(207,121,8);
    border-color: transparent;
    margin-bottom: 5px;
}
</style>