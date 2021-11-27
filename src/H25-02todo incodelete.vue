<template>
  <div>
      <form @submit.prevent="addTodo()">
          <div>
              <label>
                  What Todo?<input type="text" v-model="text">
              </label>
          </div>
          <div>
              <button>Add</button>
          </div>
      </form>
      <div v-for="item in todos" :key="item.id">
          <label>
              <input type="checkbox" :checked="item.done" @click="toggleTodo(item)"><span>{{item.text}}</span>
          </label>
      </div>
  </div>
</template>

<script>
const host='https://camt-todoapi.pair-co.com/users/joypimon/todos'

    
    
    const deleteURL=`${host}`
    fetch({
        method:'DELETE',
        url:deleteURL,
    })
export default {
    data(){
        return{
            text:'',
            todos:[],
        }
    },
    methods:{
        addTodo(){
            const createURL=`${host}`
            fetch(createURL,{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({text:this.text})})
            .then(()=>{this.loadTodos()})
            .catch(err=>{alert(err)})
        },
        loadTodos(){
            const listURL=`${host}`
            fetch(listURL,{method:'GET'})
            .then(response=>response.json())
            .then(todosData=>{this.todos = todosData})
        },
        toggleTodo(item){
            const updateURL=`${host}/${item.id}`
            fetch(updateURL,{method:'PUT',headers:{'Content-Type':'application/json'},body:JSON.stringify({...item,done:!item.done})})
            .then(()=>{this.loadTodos()})
            .catch(err=>{alert(err)})
        }
    },
    mounted(){
        this.loadTodos()
    }
}
</script>

<style>

</style>