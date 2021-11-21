<template>
  <div>
    <div class="foodListrecommends">
      <div v-for="(food, i) in foodList.recommends" :key="i">
        <img :src="food.image" alt="" class="menuimg" />
        <div>
          <p class="foodtitle">{{ food.title }}</p>
          <p class="foodprice">{{ food.price }} Baht</p>
          <button @click="addToCart(food)"><img :src="plusimg" class="plusimg" /></button>
          <p class="fooddesscrip">{{ food.desscription }}</p>
        </div>
      </div>
    </div>
    <div class="foodListrest">
      <div v-for="(food, i) in foodList.rest" :key="i">
        <img :src="food.image" alt="" class="menuimg" />
        <p>{{ food.title }}</p>
        <p>{{ food.desscription }}</p>
        <p>{{ food.price }} Baht</p>
        <button @click="addToCart(food)">+ เพิ่ม</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["PListfoodp"],
  data() {
    return {
      plusimg: require("../assets/plus.png"),
    }
  },
  computed: {
    foodList() {
      const recommends = []
      const rest = []
      for (let i = 0; i < this.PListfoodp.length; i++) {
        if (i <= 1) {
          recommends.push(this.PListfoodp[i])
        } else {
          rest.push(this.PListfoodp[i])
        }
      }
      return {
        recommends: recommends,
        rest: rest,
      };
    },
  },
  methods: {
    addToCart(food) {
      this.$emit("add:tocart", food)
    },
  },
}
</script>

<style>
.foodListrecommends {
  display: grid;
  grid-template-columns: 50% 50%;
}
.foodListrecommends div {
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin: 16px;
  border-radius: 20px;
}
.foodListrecommends div div {
  margin: 0;
  display: grid;
  grid-template-columns: 70% 20% 10%;
}
.foodListrecommends div div button {
  background-color: white;
  border-radius: 60%;
}
.foodListrest {
  display: grid;
  grid-template-columns: 25% 25% 25% 25%;
}
.foodListrest div {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin: 16px;
  border-radius: 20px;
}
.foodListrest div button {
  width: 100%;
}
.menuimg {
  width: 100%;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}
.plusimg {
  width: 100%;
}
</style>