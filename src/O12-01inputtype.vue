<template>
  <div>
      <div>
          <div>Name</div>
          <input type="text" v-model.trim="name">
          <button @click="submit('name')">Submit</button>
      </div>
      <div>
          <div>Age</div>
          <input type="number" v-model.number="age">
          <button @click="submit('age')">Submit</button>
      </div>
      <div>
          <div>Address</div>
          <textarea cols="30" rows="10" v-model.trim="address"></textarea>
          <button @click="submit('address')">Submit</button>
      </div>
      <div>
          <h1>สร้าง Text Area เกี่ยวกับตัวเอง</h1>
          <textarea cols="30" rows="10" v-model.trim="aboutMe"></textarea>
          <button @click="submit('aboutMe')">Submit</button>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            name:'',
            age:0,
            address:'',
            aboutMe:'',
        }
    },
    methods:{
        submit(inputName){
            console.log(inputName,this[inputName])
        }
    }
}
</script>

<style>

</style>