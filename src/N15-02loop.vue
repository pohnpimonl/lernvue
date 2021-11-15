<template>
  <div>
      <form @submit.prevent="run">
          <div>
              <label for="divider">ตัวหาร</label>
              <input id="divider" type="number" v-model.number="divider">
          </div>
          <div>
              <label for="to">นับไปจนถึง</label>
              <input id="to" type="number" v-model.number="to">
          </div>
          <button type="submit">Start</button>
          {{result}}
      </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            divider:0,
            to:0,
            result:[],
        }
    },
    methods:{
        run(){
            if(this.divider<=0){
                alert('Please input')
                return
            }
            else if(this.to<=0){
                alert('Please input')
                return
            }
            const a = []
            let i =1
            while (i<=this.to){
                if(i%this.divider===0){
                    a.push(i)
                }
                i++
            }
            this.result=a
        }
    }
}
</script>

<style>

</style>