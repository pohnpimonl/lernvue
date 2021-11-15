<template>
  <div>{{odds()}}</div>
</template>

<script>
export default {
    methods:{
        odds(){
            let i=1
            let count = 0
            while(i<=560){
                if(i%2===1){
                    count++
                }
                i++
            }
            return count
        }
    }
}
</script>

<style>

</style>