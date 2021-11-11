<template>
  <body>
      <div>
          <button @click="to(1)">food</button>
          <button @click="to(2)">login</button>
          <button @click="to(3)">listbuy</button>
          <span v-show="cart">1</span>
      </div>
      <div>
          <div v-if="tab===1">
              <h1>List Food</h1>
              <div>
                  <img :src="menu1.image" alt="" class="imgmenu">
                  <h2>{{menu1.title}}</h2>
                  <h4>{{menu1.desscription}}</h4>
                  <h4>{{menu1.price}} Baht</h4>
                  <button @click="addToCart(menu1)"><img :src="plus" class="plus"></button>
              </div>
              <div>
                  <img :src="menu2.image" alt="" class="imgmenu">
                  <h2>{{menu2.title}}</h2>
                  <h4>{{menu2.desscription}}</h4>
                  <h4>{{menu2.price}} Baht</h4>
                  <button @click="addToCart(menu2)"><img :src="plus" class="plus"></button>
              </div>
          </div>
          <div v-if="tab===2">
              <h1></h1>
              <div>
                  <input type="email">
              </div>
              <div>
                  <input type="password">
              </div>
              <div>
                  <button>Regis</button>
                  <button>Login</button>
              </div>
          </div>
          <div v-if="tab===3">
              <h2>Cart</h2>
              <div v-if="cart">
                  <img :src="cart.image" alt="" class="imgmenu">
                  <h2>{{cart.title}}</h2>
                  <h4>{{cart.desscription}}</h4>
                  <h4>{{cart.price}} Baht</h4>
              </div>
          </div>
      </div>
    
  </body>
</template>

<script>
export default {
    data(){
        return{
            tab:0,
            menu1:{
                image:require("./assets/01ปลากะพงทอดราดพริก3รส.jpg"),
                title:'ปลากะพงทอดราดพริก 3 รส',
                desscription:'ปลากะพงทอดราดพริก 3 รส',
                price:300,
            },
            menu2:{
                image:require("./assets/02ปูเนื้อผัดพริกไทยดำ.jpg"),
                title:'ปูเนื้อผัดพริกไทยดำ',
                desscription:'ปูเนื้อผัดพริกไทยดำ',
                price:500,
            },
            plus:require("./assets/plus.png"),
            cart:null,
        }
    },
    methods:{
        to(page){
            if(this.tab===page){
                this.tab = 0
            } else{
                this.tab=page
            }
        },
        addToCart(food){
            this.cart=food
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
</style>