<template>
    <div class="main">
      <div class="logo">
      <img src="./assets/logo.jpg" />
    </div>
    <div class="navmenu">
      <button :class="tab === 1 ? 'activeMenu' : 'defaultMenu'" @click="to(1)">อาหาร</button>
      <button :class="tab === 2 ? 'activeMenu' : 'defaultMenu'" @click="to(2)">สมาชิก</button>
      <button :class="tab === 3 ? 'activeMenu' : 'defaultMenu'" @click="to(3)">รายการสั่งซื้อ</button>
      <span v-show="cart.length">{{ cart.length }}</span>
    </div>
    <div>
      <div v-if="tab === 1">
        <h2>รายการอาหาร</h2>
        <h3>recommends</h3>
        <div class="grid-container1">
          <div v-for="(food, i) in foodList.recommends" :key="i">
            <img :src="food.image" alt="" class="menuimg"/>
            <p>{{ food.title }}</p>
            <p>{{ food.desscription }}</p>
            <p>{{ food.price }} Baht</p>
            <button @click="addToCart(food)"><img :src="plus" class="plusimg" /></button>
          </div>
        </div>
        <h3>other</h3>
        <div class="grid-container2">
          <div v-for="(food, i) in foodList.rest" :key="i">
            <img :src="food.image" alt="" class="menuimg" />
            <p>{{ food.title }}</p>
            <p>{{ food.desscription }}</p>
            <p>{{ food.price }} Baht</p>
            <button @click="addToCart(food)"><img :src="plus" class="plusimg" /></button>
          </div>
        </div>
      </div>
      <div v-if="tab === 2" class="formmemberl">
        <form @submit.prevent="submit">
          <h2>Member</h2>
          <div>
            <input type="email" v-model="user.email" required />
          </div>
          <div>
            <input type="password" v-model="user.password" required />
          </div>
          <div>
            <button type="button">Regis</button>
            <button type="submit">Login</button>
          </div>
        </form>
      </div>
      <div v-if="tab === 3">
        <h2>Cart</h2>
        <div v-for="(each, i) in cart" :key="i">
          <img :src="each.food.image" alt="" class="menuimg" />
          <h4>{{ each.food.title }}</h4>
          <h5>{{ each.food.desscription }}</h5>
          <h6>{{ each.food.price }} Baht</h6>
          <button @click="removeFromCret(each)">---</button>
        </div>
        <div>
          <h3>Total{{ total }}Baht</h3>
        </div>
      </div>
    </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      tab: 2,
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
      plus: require("./assets/plus.png"),
      cart: [],
      user: {
        email: "",
        password: "",
      },
    };
  },
  computed: {
    total() {
      let total = 0;
      for (let i = 0; i < this.cart.length; i++) {
        total += this.cart[i].food.price;
      }
      return total;
    },
    foodList() {
      const recommends = []
      const rest = []
      for (let i = 0; i < this.foods.length; i++) {
        if (i <= 5) {
          recommends.push(this.foods[i])
        } else {
          rest.push(this.foods[i])
        }
      }
      return {
        recommends: recommends,
        rest: rest,
      }
    },
  },
  watch: {
    total(newValue, oldValue) {
      if (newValue >= 10000 && oldValue < 10000) {
        alert(">=10000");
      } else if (newValue >= 4000 && oldValue < 4000) {
        alert(">=4000");
      } else if (newValue >= 2000 && oldValue < 2000) {
        alert(">=2000");
      }
    },
  },
  methods: {
    to(page) {
      if (this.tab === page) {
        this.tab = 0;
      } else {
        this.tab = page;
      }
    },
    addToCart(food) {
      // {
      //   id,
      //   food:{
      //     title,
      //     desscription,
      //     price,
      //     image
      //   }
      // }
      this.cart.push({
        id: this.id,
        food: food,
      });
      this.id++;
    },
    removeFromCret(cartItem) {
      const cart = [];
      for (let i = 0; i < this.cart.length; i++) {
        const current = this.cart[i];
        if (cartItem.id !== current.id) {
          cart.push(current);
        }
      }
      this.cart = cart;
    },
    submit() {
      // if(this.user.email&&this.user.password){
      //     alert('Login Success')
      // }else{
      //     alert('Please Check Input')
      // }
      alert("Login Success");
    },
  },
};
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
body{
  background: linear-gradient(rgba(255,255,255,0.75),rgba(255,255,255,0.75)),url('./assets/bg.jpg');
  background-size: auto;
  background-attachment: fixed;
  width: 100vw;
  height: 100vh;
}
.main{
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 800px;
  border: solid red;
}
.logo{
  text-align: center;
  height: 300px;
  padding: 50px 0;
}
.logo img{
  height: 100%;
}
.navmenu{
  text-align: center;
}
.activeMenu {
  background-color: crimson;
  color: white;
}
.defaultMenu {
  background-color: #ededed;
  border: none;
}
.grid-container1{
  display: grid;
  grid-template-columns: auto auto;
  grid-gap: 10px;
  padding: 10px;
}
.grid-container1 div {
  text-align: center;
  padding: 20px 0;
  border: solid red;
}
.grid-container1 div img{
  width: 100%;
}
.grid-container2 {
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-gap: 10px;
  padding: 10px;
}
.grid-container2 > div {
  text-align: center;
  padding: 20px 0;
  border: solid red;
}
.grid-container2 div img{
  width: 100%;
}
.plusimg{
  height: 1cm;
}
</style>