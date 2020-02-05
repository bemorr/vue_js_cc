<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" name="title" v-model="title" placeholder="Add Todo....">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ""
        }
    },
    methods: {
        addTodo() {
            const newTodo = {
                title: this.title,
                completed: false
            }
        // send addTodo() up to App.vue(parent)
        this.$emit("add-todo", newTodo)
    
        this.title = "";
        }
    }
}
</script>

<style scoped>

form {
    display: flex;
}

input[type="text"] {
    flex: 10px;
    padding: 5px;
}

</style>>
