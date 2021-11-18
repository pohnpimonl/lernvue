<template>
<div>
    <form @submit.prevent="submitTodo">
        <h1>Todo</h1>
        <input type="text" v-model="todo" required>
        <button type="submit">Submit</button>
    </form>
    <div>
        <ul>
            <li v-for="todo in todoList" :key="todo.id">
                <span>{{todo.task}}</span>
                <input @change="remove(todo)" type="checkbox" v-model="todo.isDone">
            </li>
        </ul>
        <button @click="reverse">reverse</button>
    </div>
    {{todoList}}
</div>
</template>

<script>
export default {
    data(){
        return{
            id: 1,
            todo:'',
            todoList:[],
        }
    },
    methods:{
        submitTodo(){
            this.todoList.push({
                id: this.id,
                task: this.todo,
                isDone: false,
            })
            this.id++
            this.todo=null
        },
        remove(todo){
            const notDoneTasks = []
            for(let i=0;i<this.todoList.length;i++){
              const current = this.todoList[i]
              if(current.id !== todo.id){
                notDoneTasks.push(current)
              }
            }
            this.todoList = notDoneTasks
        },
        reverse(){
            this.todoList.reverse()
        },
    }
}
</script>

<style>

</style>