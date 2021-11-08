<template>

      <section>
        My Name : {{name}}
        <button @click="setName">Set Name</button><br>
        Popcat : {{count}}
        <button @click="setCount">Click</button>
      </section>
      

</template>

<script>

export default {
  data(){
    return{
      name:'',
      count:0

    }
  },
  methods:{
    setName(){
      this.name = prompt("Input Name : ")
    },
    setCount(){
      this.count++
    }
  },
}
</script>

<style>

</style>
