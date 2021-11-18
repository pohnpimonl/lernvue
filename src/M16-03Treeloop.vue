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
            while(i<10){
                let j=0
                let leaves = ''
                while(j<10){
                    if(j<=i){
                        leaves+='*'
                    }else{
                        break
                    }
                    j++
                }
                console.log(leaves)
                i++
            }
        }
    }
}
</script>

<style>

</style>