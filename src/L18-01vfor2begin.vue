<template>
  <div>
      <div v-for="(item, i) in 10" :key="i">
          {{item}}->{{i}}
      </div>
      <div v-for="(score, i) in scores" :key="i">
          scores[{{i}}] ->{{score}}
          <div v-for="(item, j) in 10" :key="j">
              loop ชั้นใน {{item}}
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            scores:[50,44,12,89,90],
        }
    }
}
</script>

<style>

</style>