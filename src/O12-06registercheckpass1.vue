
<template>
  <div>
      <form @submit.prevent="submit">
          <div class="inputContainer">
              <div class="inputTitle">Name</div>
              <input type="text" v-model.trim="name" required>
          </div>
          <div class="inputContainer">
              <div class="inputTitle">Tel</div>
              <input type="text" v-model.trim="phone" required>
          </div>
          <div class="inputContainer">
              <div class="inputTitle">Email</div>
              <input type="email" v-model="email" required>
          </div>
          <div class="inputContainer">
              <div class="inputTitle">password</div>
              <input type="password" v-model.trim="password" required>
          </div>
          <div class="inputContainer">
              <div class="inputTitle">re-password</div>
              <input type="password" v-model.trim="confirmPassword" required>
          </div>
          <button type="submit">Register</button>
      </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            name:'',
            phone:'',
            email:'',
            password:'',
            confirmPassword:'',
        }
    },
    methods:{
        submit(){
            if(this.password ===this.confirmPassword){
                alert('Register Success')
            }else{
                alert('Password Again !')
            }
            
        }
    }
}
</script>

<style>
.inputContainer{
    margin: 16px;
}
</style>