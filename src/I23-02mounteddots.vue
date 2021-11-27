<template>
  <div>
      <div>Do you love croissant?</div>
      <div v-show="!answered">Well{{dots}}</div>
      <div>{{answer}}</div>
      <div>
          <!-- <button @click="!clicked && (answer = 'Yes I love croissant') && (clicked= true)">Yes</button>
          <button @click="!clicked && (answer = 'No I don\' like croissant') && (clicked= true)">No</button> -->
          <button @click="setAnswer('Yes I love croissant')">Yes</button>
          <button @click="setAnswer('No I don\' like croissant')">No</button>
          <button @click="reset()">Again</button>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            answered:false,
            answer:'',
            dots:'.',
        }
    },
    mounted(){
        this.id = setInterval(()=>{
            if(this.dots.length>2){
                this.dots='.'
            }else{
                this.dots+='.'
            }
        },1000)
    },
    unmounter(){
        clearInterval(this.id)
    },
    methods:{
        setAnswer(text){
            if(this.answered){
                return 
            }
            this.answer=text
            this.answered=true
        },
        reset(){
            this.answer=''
            this.answered=false
        }
    }
}
</script>

<style>

</style>