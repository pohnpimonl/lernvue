
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
              <input type="password" v-model.trim="password" @change="handlePasswordChange" required>
              <p v-show="isPasswordError" class="errorMessage">re-password Again !</p>
          </div>
          <div class="inputContainer">
              <div class="inputTitle">re-password</div>
              <input type="password" v-model.trim="confirmPassword" @change="handlePasswordChange" required>
              <p v-show="isPasswordError" class="errorMessage">re-password Again !</p>
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
            isPasswordError:false,
        }
    },
    methods:{
        submit(){
            if(this.password ===this.confirmPassword){
                alert('Register Success')
            }else{
                alert('Password Again !')
            }
            
        },
        handlePasswordChange(){
          if(this.password !==this.confirmPassword){
            this.isPasswordError=true
          }else{
            this.isPasswordError=false
          }
        }
    }
}
</script>

<style>
.inputContainer{
    margin: 16px;
}
.errorMessage{
  color: red;
}
</style>