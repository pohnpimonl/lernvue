<template>
  <div>
      <div>
          <h1>{{score}}</h1>
      </div>
      <div>
          <button v-if="!(score+3>100)" @click="plus(3)">+3</button>
          <button v-if="!(score+5>100)" @click="plus(5)">+5</button>
          <button v-if="!(score+10>100)" @click="plus(10)">+10</button>
      </div>
      <div>
          <button v-if="!(score-3>100)" @click="minus(3)">-3</button>
          <button v-if="!(score-5>100)" @click="minus(5)">-5</button>
          <button v-if="!(score-10>100)" @click="minus(10)">-10</button>
      </div>
      <div class="red">
          <p>{{grade()}}</p>
      </div>
      <div>
          <p v-if="score>=50 && score <60">D</p>
          <p v-if="score>=60 && score <70">C</p>
          <p v-if="score>=70 && score <80">B</p>
          <p v-if="score>=80">A</p>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            score:0,
        }
    },
    methods:{
        grade(){
            if(this.score>=50 && this.score <60){
                return 'D'
            }
            if(this.score>=60 && this.score <70){
                return 'C'
            }
            if(this.score>=70 && this.score <80){
                return 'B'
            }
            if(this.score>=80){
                return 'A'
            }
        },
        plus(score){
            this.score+=score
        },
        minus(score){
            this.score-=score
        }
    }
}
</script>

<style>
.red{
    background-color: red;
}
</style>