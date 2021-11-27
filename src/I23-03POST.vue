<template>
  <div>
      <button @click="loadData()">Click Me</button>
      {{data}}
      <!-- <div v-for="item in data" :key="item.id"></div>
      <h5>{{item.title}}</h5> -->
  </div>
</template>

<script>
export default {
    data(){
        return{
            data:[],
        }
    },
    methods:{
        loadData(){
            fetch('https://jsonplaceholder.typicode.com/posts')
            .then((response)=>{
                return response.json()
            })
            .then((data)=>{
                this.data=data
            })
            .catch((err)=>{
                alert(err)
            })
        }
    }
}
</script>

<style>

</style>