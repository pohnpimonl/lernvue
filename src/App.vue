<template>
  <div>
    <h1><b>Pop Cat</b></h1>
    <p class="ppop">{{ pop.count }}</p>
    <button @click="addPop(0)">POP IT</button><br />
    <p v-if="pop.show"><img v-if="pop.countpop <= 19" :src="pop.pic1" /></p>
    <p v-if="!pop.show"><img v-if="pop.countpop <= 19" :src="pop.pic2" /></p>
    <p v-if="pop.show"><img v-if="(pop.countpop >= 20) && (pop.countpop <= 49)" :src="pop.pic3" /></p>
    <p v-if="!pop.show"><img v-if="(pop.countpop >= 20) && (pop.countpop <= 49)" :src="pop.pic4" /></p>
    <p v-if="pop.show"><img v-if="pop.countpop > 49" :src="pop.pic1" /></p>
    <p v-if="!pop.show"><img v-if="pop.countpop > 49" :src="pop.pic2" /></p>
  </div></template>
<script>
export default {
  data() {
    return {
      pop: {
        count: 0,countpop: 0,
        pic1: "https://www.img.in.th/images/ac4e0ad2d41b99d878dbf117be8567be.jpg",
        pic2: "https://www.img.in.th/images/533b8fb829b109288df250a57e748b11.jpg",
        pic3: "https://www.img.in.th/images/b72310fce825a2238bad7c0df0903e7b.jpg",
        pic4: "https://www.img.in.th/images/81ad471177ec681234dda3a85964ea44.jpg",
        show: true,
      },};},
  methods: {
    addPop(pops) {
      this.pop.show=this.pop.count%2===1
      this.pop.count++
      this.pop.countpop++
      pops=this.pop.countpop
      if(pops>49)
      this.pop.countpop=0
    },
  },
};
</script>

<style>
img {
  height: 15cm;
}
.ppop {
  font-size: 20px;
  margin-left: 0.5cm;
}
</style>