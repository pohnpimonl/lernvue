<template>
  <div id="app">
      <div v-show="show">
      <div>{{me.name}}</div>
      <div>{{me.home}}</div>
      </div>
      <div v-show="!show">
      <div>xxxxxxxxx</div>
      <div>xxxxxxxxx</div>
      </div>
      <button @click="toggle()">Show/Hide</button>
      <!-- <button @click="toggle(false)">Hide</button> -->
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
        count:0,
        }
    },
    methods:{
        toggle: function(){
            this.show=this.count%2===1
            this.count++
        },
    }
}
</script>
<style>
</style>