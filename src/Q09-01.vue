<template>
  <div id="app">
      <div v-show="show" class="name">
      <div>{{me.name}}</div>
      <div>{{me.home}}</div>
      </div>
      <button @click="toggle(true)">Show</button>
      <button @click="toggle(false)">Hide</button>
  </div>
</template>
<script>
export default {
    data:function(){
        return{
            
            me:{
            name: 'Joy Pimon',
            home: 'Nonthaburi',
        },
        show: true,
        }
    },
    methods:{
        toggle: function(isShow){
            this.show = isShow
        },
    }
}
</script>
<style>
.name{
    height: 50px;
}
</style>