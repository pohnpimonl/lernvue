<template>
  <div class="main">
    <div><p-logo-menu :PLogoMenup="tab" :cart="cart" @menu:chenge="to" /></div>
    <div v-if="tab === 1"><p-listfood :PListfoodp="foods" @add:tocart="addToCart" /></div>
    <div v-if="tab === 2"><p-member /></div>
    <div v-if="tab === 3"><p-cart :PCartp="cart" @remove:fromcart="removeFromCart" /></div>
  </div>
</template>

<script>
import PLogoMenu from './components/PLogoMenu.vue'
import PListfood from './components/PListfood.vue'
import PMember from './components/PMember.vue'
import PCart from './components/PCart.vue'
export default {
  components: {
    PLogoMenu,PListfood,PMember,PCart,
  },
  data() {
    return {
      tab: 1,
      id: 1,
      foods: [
        {
          image: require("./assets/01ปลากะพงทอดราดพริก3รส.jpg"),
          title: "ปลากะพงทอดราดพริก 3 รส",
          desscription: "ปลากะพงทอดราดพริก 3 รส",
          price: 550,
        },
        {
          image: require("./assets/02ปูเนื้อผัดพริกไทยดำ.jpg"),
          title: "ปูเนื้อผัดพริกไทยดำ",
          desscription: "ปูเนื้อผัดพริกไทยดำ",
          price: 600,
        },
        {
          image: require("./assets/03กุ้งลายเสือจัมโบ้ราดพริก.jpg"),
          title: "กุ้งลายเสือจัมโบ้ราดพริก",
          desscription: "กุ้งลายเสือจัมโบ้ราดพริก",
          price: 900,
        },
        {
          image: require("./assets/04ต้มยำกุ้ง น้ำข้น.jpg"),
          title: "ต้มยำกุ้ง น้ำข้น",
          desscription: "ต้มยำกุ้ง น้ำข้น",
          price: 580,
        },
        {
          image: require("./assets/05หอยแมลงภู่นิวซีแลนด์อบเนย.jpg"),
          title: "หอยแมลงภู่นิวซีแลนด์อบเนย",
          desscription: "หอยแมลงภู่นิวซีแลนด์อบเนย",
          price: 550,
        },
        {
          image: require("./assets/06ปลาหมึกไข่นึ่งมะนาว.jpg"),
          title: "ปลาหมึกไข่นึ่งมะนาว",
          desscription: "ปลาหมึกไข่นึ่งมะนาว",
          price: 270,
        },
        {
          image: require("./assets/07ปลากะพงทอดราดน้ำปลา.jpg"),
          title: "ปลากะพงทอดราดน้ำปลา",
          desscription: "ปลากะพงทอดราดน้ำปลา",
          price: 490,
        },
        {
          image: require("./assets/08ปูไข่ดอง.jpg"),
          title: "ปูไข่ดอง",
          desscription: "ปูไข่ดอง",
          price: 720,
        },
        {
          image: require("./assets/09กุ้งแม่น้ำเผา.jpg"),
          title: "กุ้งแม่น้ำเผา",
          desscription: "กุ้งแม่น้ำเผา ครึ่งกิโล",
          price: 1050,
        },
        {
          image: require("./assets/10หอยเชลล์ผัดฉ่า.jpg"),
          title: "หอยเชลล์ผัดฉ่า",
          desscription: "หอยเชลล์ผัดฉ่า",
          price: 250,
        },
        {
          image: require("./assets/11ปลาหมึกผัดไข่เค็ม.jpg"),
          title: "ปลาหมึกผัดไข่เค็ม",
          desscription: "ปลาหมึกผัดไข่เค็ม",
          price: 240,
        },
        {
          image: require("./assets/12ยอดฟักแม้วผัดปลาเค็ม.jpg"),
          title: "ยอดฟักแม้วผัดปลาเค็ม",
          desscription: "ยอดฟักแม้วผัดปลาเค็ม",
          price: 180,
        },
        {
          image: require("./assets/13แกงส้มไข่ปลาเรียวเซียว.jpg"),
          title: "แกงส้มไข่ปลาเรียวเซียว",
          desscription: "แกงส้มไข่ปลาเรียวเซียว",
          price: 690,
        },
        {
          image: require("./assets/14ปูม้านึ่ง.jpg"),
          title: "ปูม้านึ่ง",
          desscription: "ปูม้านึ่ง",
          price: 860,
        },
        {
          image: require("./assets/15กุ้งแชร์บ๊วยผัดพริกไทยดำ.jpg"),
          title: "กุ้งแชร์บ๊วยผัดพริกไทยดำ",
          desscription: "กุ้งแชร์บ๊วยผัดพริกไทยดำ",
          price: 800,
        },
        {
          image: require("./assets/16หอยเชลล์อบเนย.jpg"),
          title: "หอยเชลล์อบเนย",
          desscription: "หอยเชลล์อบเนย",
          price: 280,
        },
        {
          image: require("./assets/17ปลาหมึกแดดเดียว.jpg"),
          title: "ปลาหมึกแดดเดียว",
          desscription: "ปลาหมึกแดดเดียว",
          price: 200,
        },
        {
          image: require("./assets/18ข้าวผัดปูพรีเมียม.jpg"),
          title: "ข้าวผัดปูพรีเมียม",
          desscription: "ข้าวผัดปูพรีเมียม",
          price: 180,
        },
      ],
      cart: [],
    }
  },
  computed: {},
  methods: {
    to(page) {
      if (this.tab === page) {
        this.tab = 0
      } else {
        this.tab = page
      }
    },
    addToCart(food) {
      this.cart.push({
        id: this.id,
        food: food,
      })
      this.id++
    },
    removeFromCart(cartItem) {
      const cart = []
      for (let i = 0; i < this.cart.length; i++) {
        const current = this.cart[i]
        if (cartItem.id !== current.id) {
          cart.push(current)
        }
      }
      this.cart = cart
    },
  },
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Prompt&display=swap");
* {
  margin: 0;
  padding: 0;
  list-style: none;
  box-sizing: border-box;
  font-family: "Prompt", sans-serif;
}
body {
  background: linear-gradient( rgba(255, 255, 255, 0.75),rgba(255, 255, 255, 0.75)),url("./assets/bg.jpg");
  background-size: auto;
  background-attachment: fixed;
  width: 100vw;
  height: 100vh;
}
.main {
  width: 1180px;
  margin-left: auto;
  margin-right: auto;
}
</style>