<template>
<div>
    <form @submit.prevent="submitTodo">
        <h1>Add Todo</h1>
        <input type="text" v-model="todo" required>
        <button type="submit">Submit</button>
    </form>
    <div>{{todoList}}</div>
</div>
</template>

<script>
export default {
    data(){
        return{
            todo:'',
            todoList:[],
        }
    },
    methods:{
        submitTodo(){
            this.todoList.push(this.todo)
            this.todo=null
        }
    }
}
</script>

<style>

</style>