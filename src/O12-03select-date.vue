<template>
  <div>
      <div>
          <h1>Select</h1>
          <div>Province</div>
           <select v-model="province">
              <option value="" disabled> Please select</option>
              <option value="cm">Chaingmai</option>
              <option >Bangkok</option>
              <option >konkan</option>
          </select>
          <button @click="submit('province')">Submit</button>
      </div>
      <div>
          <h1>Select Country 3 pcs</h1>
          <select v-model="country">
              <option>Thai</option>
              <option>England</option>
              <option>America</option>
          </select>
          <button @click="submit('country')">Submit</button>
      </div>
      <div>
          <h1>Date</h1>
          <input type="date" v-model="dob">
          <button @click="submit('dob')">Submit</button>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            province:'',
            country:'',
            dob:'',

        }
    },
    methods:{
        submit(inputName){
            console.log(inputName,this[inputName])
            if(inputName==='dob'){
                console.log('date object',new Date(this.dob))
            }
        }
    }
}
</script>

<style>

</style>