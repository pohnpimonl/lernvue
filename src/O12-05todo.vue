<template>
<div>
    <form @submit.prevent="submitTodo">
        <h1>Add Todo</h1>
        <input type="text" v-model="todo" required>
        <button type="submit">Submit</button>
    </form>
</div>
</template>

<script>
export default {
    data(){
        return{
            todo:'',
        }
    },
    methods:{
        submitTodo(){
            alert('Success')
        }
    }
}
</script>

<style>

</style>