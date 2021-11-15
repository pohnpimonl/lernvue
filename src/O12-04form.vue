<template>
  <div>
      <form @submit.prevent="submit">
          <h4>1. input under form</h4>
          <h4>2. submit 1 under botton</h4>
          <div>
              <div>email</div>
              <input type="email" v-model="email" required>
              <button type="button" @click="logData('email')">log</button>
          </div>
          <button type="submit">Submit</button>
      </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            email:'',
        }
    },
    methods:{
        submit(){
            alert('Success')
        },
        logData(inputName){
            console.log(inputName,this[inputName])
        }
    }
}
</script>

<style>

</style>