<template>
  <div>
      <div>
          <button :class="tab===1?'activeMenu':'defaultMenu'" @click="to(1)">food</button>
          <button :class="tab===2?'activeMenu':'defaultMenu'" @click="to(2)">login</button>
          <button :class="tab===3?'activeMenu':'defaultMenu'" @click="to(3)">listbuy</button>
          <span v-show="cart.length">{{cart.length}}</span>
      </div>
      <div>
          <div v-if="tab===1">
              <h1>List Food</h1>
              <div>
                  <img :src="foods[0].image" alt="" class="imgmenu">
                  <h2>{{foods[0].title}}</h2>
                  <h4>{{foods[0].desscription}}</h4>
                  <h4>{{foods[0].price}} Baht</h4>
                  <button @click="addToCart(foods[0])"><img :src="plus" class="plus"></button>
              </div>
              <div>
                  <img :src="foods[1].image" alt="" class="imgmenu">
                  <h2>{{foods[1].title}}</h2>
                  <h4>{{foods[1].desscription}}</h4>
                  <h4>{{foods[1].price}} Baht</h4>
                  <button @click="addToCart(foods[1])"><img :src="plus" class="plus"></button>
              </div>
              <div>
                  <img :src="foods[2].image" alt="" class="imgmenu">
                  <h2>{{foods[2].title}}</h2>
                  <h4>{{foods[2].desscription}}</h4>
                  <h4>{{foods[2].price}} Baht</h4>
                  <button @click="addToCart(foods[2])"><img :src="plus" class="plus"></button>
              </div>
              <div>
                  <img :src="foods[3].image" alt="" class="imgmenu">
                  <h2>{{foods[3].title}}</h2>
                  <h4>{{foods[3].desscription}}</h4>
                  <h4>{{foods[3].price}} Baht</h4>
                  <button @click="addToCart(foods[3])"><img :src="plus" class="plus"></button>
              </div>
              <div>
                  <img :src="foods[4].image" alt="" class="imgmenu">
                  <h2>{{foods[4].title}}</h2>
                  <h4>{{foods[4].desscription}}</h4>
                  <h4>{{foods[4].price}} Baht</h4>
                  <button @click="addToCart(foods[4])"><img :src="plus" class="plus"></button>
              </div>
          </div>
          <div v-if="tab===2">
              <form @submit.prevent="submit">
                  <h1>Member</h1>
                  <div>
                      <input type="email" v-model="user.email" required>
                  </div>
                  <div>
                      <input type="password" v-model="user.password" required>
                  </div>
                  <div>
                      <button type="button">Regis</button>
                      <button type="submit">Login</button>
                  </div>
              </form>
          </div>
          <div v-if="tab===3">
              <h1>Cart</h1>
              <div v-if="cart">
                  <img :src="cart.image" alt="" class="imgmenu">
                  <h2>{{cart.title}}</h2>
                  <h4>{{cart.desscription}}</h4>
                  <h4>{{cart.price}} Baht</h4>
              </div>
          </div>
      </div>
    
  </div>
</template>

<script>
export default {
    data(){
        return{
            tab:2,
            foods:[
              {
                image:require("./assets/01ปลากะพงทอดราดพริก3รส.jpg"),
                title:'ปลากะพงทอดราดพริก 3 รส',
                desscription:'ปลากะพงทอดราดพริก 3 รส',
                price:300,
            },
            {
                image:require("./assets/02ปูเนื้อผัดพริกไทยดำ.jpg"),
                title:'ปูเนื้อผัดพริกไทยดำ',
                desscription:'ปูเนื้อผัดพริกไทยดำ',
                price:500,
            },
            {
                image:require("./assets/03กุ้งลายเสือจัมโบ้ราดพริก.jpg"),
                title:'กุ้งลายเสือจัมโบ้ราดพริก',
                desscription:'กุ้งลายเสือจัมโบ้ราดพริก',
                price:500,
            },
            {
                image:require("./assets/04ต้มยำกุ้ง น้ำข้น.jpg"),
                title:'ต้มยำกุ้ง น้ำข้น',
                desscription:'ต้มยำกุ้ง น้ำข้น',
                price:500,
            },
            {
                image:require("./assets/05หอยแมลงภู่นิวซีแลนด์อบเนย.jpg"),
                title:'หอยแมลงภู่นิวซีแลนด์อบเนย',
                desscription:'หอยแมลงภู่นิวซีแลนด์อบเนย',
                price:500,
            },
            ],
            plus:require("./assets/plus.png"),
            cart: [],
            user:{
                email:'',
                password:'',
            }
        }
    },
    methods:{
        // total(){
        //   let total=0
        //   let i=0
        //   while(i<this.cart.length){
        //     total+=this.cart[i].price
        //     i++
        //   }
        //   return total
        // },
        to(page){
            if(this.tab===page){
                this.tab = 0
            } else{
                this.tab=page
            }
        },
        addToCart(food){
            this.cart.push(food)
        },
        submit(){
            // if(this.user.email&&this.user.password){
            //     alert('Login Success')
            // }else{
            //     alert('Please Check Input')
            // }
            alert('Login Success')
        }
    }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kanit:wght@100&display=swap");

* {
  margin: 0;
  padding: 0;
  list-style: none;
  box-sizing: border-box;
  font-family: "Kanit", sans-serif;
  font-weight: bolder;
}
body {
  background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0.7) 0%,rgba(255, 255, 255, 0.7) 100%), url('assets/bg.jpg');
  background-size: cover;
  background-attachment: fixed;
}
.imgmenu{
    height: 5cm;
}
.plus{
    height: 1cm;
}
.activeMenu{
    background-color: crimson;
    color: white;
}
.defaultMenu{
    background-color: #ededed;
    border: none;
}
</style>