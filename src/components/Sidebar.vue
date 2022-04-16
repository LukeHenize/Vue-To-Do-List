<template>
    <div id="sidebar">
        <div class="sidebar-box">
            <h2 class="sidebar-title">
                <u>Add To-Do Item</u>
            </h2>
            <form @submit="onSubmit" id="add-item-form" class="section">
                <div class="form-item">
                    <label for="add-title">Task Name</label><br>
                    <input id="add-title" v-model="name" name="name" type="text" placeholder="Exercise" autocomplete="off"><br>
                </div>
                <div class="form-item">
                    <label for="add-desc">Task Description</label><br>
                    <textarea id="add-desc" v-model="description" name="description" autocomplete="off"></textarea><br>
                </div>
                <input type="submit" id="add-item" value="Add Task"/>
            </form>
        </div>
        <div id="completed-box" class="sidebar-box">
            <h2 class="sidebar-title">Completed Tasks</h2>
            <div id="completed-list" class="section">

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Sidebar",
    data() {
        return {
            name: "",
            description: ""
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault();

            if(!this.name) {
                alert("Please enter a valid task name!");
                return;
            }

            const newTask = {
                name: this.name,
                description: this.description,
                //timer: this.createTimer()
            }

            this.$emit("add-task", newTask);

            this.name = "";
            this.description = "";
        },
        createTimer() {
            return {ms: 0, mins: 0};
        }
    }
}
</script>

<style scoped>
div.sidebar-box {
    position: fixed;
    height: 100%;
    width: 25%;
    padding: 10px; 
    border-right: 2px solid rgb(200,200,200);
}
.section {
    border: 2px solid rgb(200,200,200);
}
h2.sidebar-title {
    text-align: center;
}
form#add-item-form {
    min-width: 150px;

    display: flex;
    flex-direction: column;
}
div.form-item {
    margin: 10px auto;

}
input, button {
    max-width: 130px;
}
textarea#add-desc {
    min-height: 50px;
    max-width: 130px;
}
input#add-item {
    width: 50%;
    margin: auto;
    margin-top: 5px;
    margin-bottom: 5px;
    background-color: rgb(207,121,8);
    border-radius: 5%;
    border-color: transparent;
}
div#completed-box {
    top: 400px;
}
div#completed-list {
    display: flex;
    flex-direction: column;
    font-size: 0.75em;
    padding: 10px;
}
</style>