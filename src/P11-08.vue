<template>
  <div>
      <div>
          <button @click="flip()">Close</button>
          <button @click="flip()">Flip</button>
      </div>
      <div v-if="isClose">
      <div class="front" v-if="side==='front'">
          front
      </div>
      <div class="back" v-else>
          back
      </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            side:'front',
            isClose: true,
        }
    },
    methods:{
        flip(){
            this.isClose=false
            this.side=this.side==='front'?'back':'front'
        }
    }
}
</script>

<style>

</style>