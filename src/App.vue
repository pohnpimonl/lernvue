<template>
  <div>
    <h1><b>Pop Cat</b></h1>
    <p>{{ pop.count }}</p>
    <button @click="addPop()">POP IT</button><br />
    <img v-if="pop.count <= 19" :src="pop.pic1" alt="pop.pic1" />
    <img v-if="pop.count >= 20 && pop.count <= 49" :src="pop.pic2" alt="pop.pic2" />
    <img v-if="pop.count > 49" :src="pop.pic1" alt="pop.pic1" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      pop: {
        count: 0,
        pic1: "https://www.img.in.th/images/ac4e0ad2d41b99d878dbf117be8567be.jpg",
        pic2: "https://www.img.in.th/images/81ad471177ec681234dda3a85964ea44.jpg",
      },
    };
  },
  methods: {
    addPop() {
      this.pop.count++;
    },
  },
};
</script>

<style>
img {
  height: 15cm;
}
p {
  font-size: 20px;
  margin-left: 0.5cm;
}
</style>