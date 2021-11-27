<template>
  <div class="carta">
    <div class="cartb">
      <h5>คุณมีรายการคำสั่งซื้อในตะกร้าทั้งหมด</h5>
      <h5>{{ PCartp.length }} รายการ</h5>
    </div>
    <div v-for="each in PCartp" :key="each.food.id" class="cartc">
        <img class="imgcart" :src="picfoods+each.food.photo" alt="" />
        <p>{{ each.food.name }}</p>
        <p>{{ each.food.shopname }}</p>
        <p>{{ each.food.price }} Baht</p>
        <button @click="removeFromCart(each)">ลบ</button>
    </div>
    <div class="cartd">
      <h3>Total{{ total }}Baht</h3>
      <button type="submit">สั่งอาหาร</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["PCartp"],
  data(){
    return{
      picfoods:'https://camt-foodapi.pair-co.com'
    }
  },
  computed: {
    total() {
      let total = 0
      for (let i = 0; i < this.PCartp.length; i++) {
        total += this.PCartp[i].food.price
      }
      return total
    },
  },
  methods: {
    removeFromCart(cartItem) {
      this.$emit("remove:fromcart", cartItem)
    },
  },
};
</script>

<style>
.carta {
  margin-top: 20px;
  width: 560px;
  margin-left: auto;
  margin-right: auto;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 20px;
}
.cartc{
  display: grid;
  grid-template-columns: 20% 30% 30% 10% 10%;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  height: 88px;
  margin: 8px 0;
  overflow: hidden;
}
.cartc button{
  background-color: #9a0606;
  color: white;
  padding: 14px 20px;
  margin: 0;
  border: none;
  border-radius: 20px;
}
.cartd button{
  background-color: #9a0606;
  color: white;
  padding: 14px 20px;
  margin: 0;
  border: none;
  border-radius: 20px;
}
.imgcart{
  width: 88px;
  height: 88px;
  border-radius: 50%;
}
.cartd{
  height: 108px;
  text-align: center;
}

</style>