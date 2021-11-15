<template>
  <body>
      <div>
          <button @click="to(1)">food</button>
          <button @click="to(2)">login</button>
          <button @click="to(3)">listbuy</button>
      </div>
      <div>
          <div v-if="tab===1">
              <h1></h1>
              <div>
                  <img src="./assets/01ปลากะพงทอดราดพริก 3 รส.jpg">
                  <h2>ปลากะพงทอดราดพริก 3 รส</h2>
                  <h4>ปลากะพงทอดราดพริก 3 รส</h4>
                  <h4>300 บาท</h4>
                  <button><img src="./assets/plus.png"></button>
              </div>
              <div>
                  <img src="./assets/02ปูเนื้อผัดพริกไทยดำ.jpg">
                  <h2>ปูเนื้อผัดพริกไทยดำ</h2>
                  <h4>ปูเนื้อผัดพริกไทยดำ</h4>
                  <h4>500 บาท</h4>
                  <button><img src="./assets/plus.png"></button>
              </div>
          </div>
          <div v-if="tab===2">
              <form>
                <h1>Member</h1>
              <div>
                  <input type="email" v-model="user.email">
              </div>
              <div>
                  <input type="password" v-model="user.password">
              </div>
              <div>
                  <button type="button">Regis</button>
                  <button type="subsit">Login</button>
              </div>
              </form>
          </div>
          <div v-if="tab===3">
              <img src="./assets/01ปลากะพงทอดราดพริก 3 รส.jpg">
              <h2>ปลากะพงทอดราดพริก 3 รส</h2>
              <h4>ปลากะพงทอดราดพริก 3 รส</h4>
              <h4>300 บาท</h4>
              <h2>total 50 Bath</h2>
          </div>
      </div>


  </body>
</template>

<script>
export default {
    data(){
        return{
            tab:0,
        }
    },
    methods:{
        to(page){
            this.tab=page
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
  background-image: linear-gradient(to bottom, rgba(255, 255, 255, 0.7) 0%,rgba(255, 255, 255, 0.7) 100%), url('assets/bg.jpg');
  background-size: cover;
  background-attachment: fixed;
}
</style>