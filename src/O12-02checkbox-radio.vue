<template>
  <div>
      <div>
          <h1>CheckBox Vaccine</h1>
      <input type="checkbox" v-model="isProtected" id="Protected">
      <label for="Protected">recrive vaccine</label>
      <button @click="submit('isProtected')">Submit</button>
      </div>
      <div>
<h1>Marry</h1>
      <input type="checkbox" v-model="isMarriaged" id="Marriaged">
      <label for="Marriaged">are you Marry?</label>
      <button @click="submit('isMarriaged')">Submit</button>
      </div>
<div>
    <h1>Radio</h1>
    <div>sex</div>
    <input type="radio" v-model="gender" value="male" id="male">
    <label for="male">mail</label>
    <input type="radio" v-model="gender" value="female" id="female">
    <label for="femaie">Female</label>
    <button @click="submit('gender')">Submit</button>
</div>
<div>
    <h1>สัตว์ที่ชื่นชอบมากที่สุด</h1>
    <input type="radio" v-model="pet" value="cat" id="cat">
    <label for="cat">Cat</label>
    <input type="radio" v-model="pet" value="dog" id="dog">
    <label for="dog">Dog</label>
    <input type="radio" v-model="pet" value="bird" id="bird">
    <label for="bird">Bird</label>
    <button @click="submit('pet')">Submit</button>
</div>
      
  </div>
</template>

<script>
export default {
    data(){
        return{
            isProtected:true,
            isMarriaged:false,
            gender:'',
            pet:'',
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