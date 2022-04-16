<template>
    <div id="page-header">
        <h1 id="title">Vue To-Do List</h1>
        <div id="counter" class="item">
            <h2 id="item-counter">
                You have {{counter == 0 ? "nothing" : counter + " tasks"}} on your to-do list!
            </h2>
        </div>
    </div>
</template>

<script>
export default {
    name: "Header",
    props: {
        counter: Number,
    }
}
</script>

<style scoped>
div#page-header {
    text-align: center;
    margin-left: 30%;
    margin-right: 3%;
}
div.item {
    background-color: #4d4d4d;
    padding: 5px;
    margin: 5px 0px 5px 0px;
}
</style>
