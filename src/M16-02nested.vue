<template>
  <div>{{nested()}}</div>
</template>

<script>
export default {
    data(){
        return{

        }
    },
    methods:{
        nested(){
            let i=0
            while(i<2){
                console.log(`first loop${i}`)
                let j=0
                while(j<2){
                    console.log(`second loop ${j}`)
                    j++
                }
                i++
            }
        }
    }
}
</script>

<style>

</style>