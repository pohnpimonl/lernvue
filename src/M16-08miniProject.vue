<template>
    <div>
        <div>
            <button @click="to(1)">เพิ่มสมาชิก</button>
            <button @click="to(2)">รายการสินค้า</button>
        </div>
        <div>
            <div v-if="tab===1">
                <form @submit.prevent="register">
                    <div>
                        <label for="formId">รหัสลูกค้า</label>
                        <input id="formId" type="text" v-model="customerForm.id" required>
                    </div>
                    <div>
                        <label for="formName">ชื่อลูกค้า</label>
                        <input id="formName" type="text" v-model="customerForm.name" required>
                    </div>
                    <button type="submit">สมัคร</button>
                </form>
                {{ customers}}
            </div>
            <div v-if="tab===2">
                <h1>รายการอาหาร</h1>
                <div>
                    <label for="orderer">ผู้สั่ง</label>
                    <input id="orderer" type="text" v-model="customerId">
                </div>
                <div>
                    <img :src="foods[0].image" alt="" class="imgmenu" />
                    <h2>{{ foods[0].title }}</h2>
                    <h4>{{ foods[0].desscription }}</h4>
                    <h4>{{ foods[0].price }} Baht</h4>
                    <button @click="addToCart(foods[0])"><img :src="plus" class="plus" /></button>
                </div>
                <div>
                    <img :src="foods[1].image" alt="" class="imgmenu" />
                    <h2>{{ foods[1].title }}</h2>
                    <h4>{{ foods[1].desscription }}</h4>
                    <h4>{{ foods[1].price }} Baht</h4>
                    <button @click="addToCart(foods[1])"><img :src="plus" class="plus" /></button>
                </div>
                <div>
                    <img :src="foods[2].image" alt="" class="imgmenu" />
                    <h2>{{ foods[2].title }}</h2>
                    <h4>{{ foods[2].desscription }}</h4>
                    <h4>{{ foods[2].price }} Baht</h4>
                    <button @click="addToCart(foods[2])"><img :src="plus" class="plus" /></button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            tab: 1,
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
            ],
            plus: require("./assets/plus.png"),
            customers:[],
            customerForm:{
                id:null,
                name:null,
            },
            customerId:null,
        }
    },
    methods:{
        to(tab){
            this.tab=tab
        },
        register(){
            const customer = {
                id: this.customerForm.id,
                name: this.customerForm.name,
                cart: [],
            }
            this.customers.push(customer)
            this.customerForm={
                id:null,
                name:null,
            }
        },
        addToCart(food){
            const customer = this.find()
            if(customer){
                customer.cart.push(food)
            }else{
                alert('Customer Not Found..')
            }
        },
        find(){
            for(let i=0;i<this.customers.length;i++){
                const customer=this.customers[i]
                if(customer.id ===this.customerId){
                    return customer
                }
            }
            return null
        },
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
  background-image: linear-gradient(
      to bottom,
      rgba(255, 255, 255, 0.7) 0%,
      rgba(255, 255, 255, 0.7) 100%
    ),
    url("assets/bg.jpg");
  background-size: cover;
  background-attachment: fixed;
}
.imgmenu {
  height: 5cm;
}
.plus {
  height: 1cm;
}
</style>