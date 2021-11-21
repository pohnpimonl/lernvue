<template>
  <div class="carta">
    <div class="cartb">
      <h5>คุณมีรายการคำสั่งซื้อในตะกร้าทั้งหมด</h5>
      <h5>{{ PCartp.length }} รายการ</h5>
      <div v-for="(each, i) in PCartp" :key="i">
        <img :src="each.food.image" alt="" class="menuimg" />
        <h4>{{ each.food.title }}</h4>
        <h5>{{ each.food.desscription }}</h5>
        <h6>{{ each.food.price }} Baht</h6>
        <button @click="removeFromCart(each)">---</button>
      </div>
      <div>
        <h3>Total{{ total }}Baht</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["PCartp"],
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
}
.cartb {
  width: 560px;
  margin-left: auto;
  margin-right: auto;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 20px;
}
.cartb div img {
  width: 100px;
}
</style>