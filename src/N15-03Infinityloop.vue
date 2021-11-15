<template>
  <div>

  </div>
</template>

<script>
export default {
    methods:{
        loop(){
            let i = 0
            let j = 0
            while (true) {
                console.log(i)
                j++
                if(j>10){
                    break
                }
            }
        }
    }
}
</script>

<style>

</style>