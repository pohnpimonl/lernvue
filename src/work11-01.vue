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
              <img src="./assets/01ปลากะพงทอดราดพริก 3 รส.jpg">
              <h2>ปลากะพงทอดราดพริก 3 รส</h2>
              <h4>ปลากะพงทอดราดพริก 3 รส</h4>
              <h4>300 บาท</h4>
              <h2>total 50 Bath</h2>
          </div>
      </div>
      <!-- <div class="list">
    <header class="topLogo">
        <img src="./assets/logo.jpg" class="logo" />
      </header>
      <nav class="topNav">
        <a href="">อาหาร</a>
        <a href="">สมาชิก</a>
        <a href="">รายการสั่งซื้อ</a>
      </nav>
      <section class="content">
        <div class="card1">
          <img src="./assets/01ปลากะพงทอดราดพริก 3 รส.jpg" id="foodpicture" />
          <div>
            <h4><b>01ปลากะพงทอดราดพริก 3 รส</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card1">
          <img src="./assets/02ปูเนื้อผัดพริกไทยดำ.jpg" id="foodpicture" />
          <div>
            <h4><b>02ปูเนื้อผัดพริกไทยดำ</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
      </section>
      <section class="content">
        <div class="card1">
          <img src="./assets/03กุ้งลายเสือจัมโบ้ราดพริก.jpg" id="foodpicture" />
          <div>
            <h4><b>03กุ้งลายเสือจัมโบ้ราดพริก</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card1">
          <img src="./assets/04ต้มยำกุ้ง น้ำข้น.jpg" id="foodpicture" />
          <div>
            <h4><b>04ต้มยำกุ้ง น้ำข้น</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
      </section>
      <section class="content">
        <div class="card1">
          <img
            src="./assets/05หอยแมลงภู่นิวซีแลนด์อบเนย.jpg" id="foodpicture" />
          <div>
            <h4><b>05หอยแมลงภู่นิวซีแลนด์อบเนย</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card1">
          <img src="./assets/06ปลาหมึกไข่นึ่งมะนาว.jpg" id="foodpicture" />
          <div>
            <h4><b>06ปลาหมึกไข่นึ่งมะนาว</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
      </section>
      <section class="content">
        <div class="card2">
          <img src="./assets/07ปลากะพงทอดราดน้ำปลา.jpg" id="foodpicture" />
          <div>
            <h4><b>07ปลากะพงทอดราดน้ำปลา</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/08ปูไข่ดอง.jpg" id="foodpicture" />
          <div>
            <h4><b>08ปูไข่ดอง</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/09กุ้งแม่น้ำเผา.jpg" id="foodpicture" />
          <div>
            <h4><b>09กุ้งแม่น้ำเผา</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/10หอยเชลล์ผัดฉ่า.jpg" id="foodpicture" />
          <div>
            <h4><b>10หอยเชลล์ผัดฉ่า</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
      </section>
      <section class="content">
        <div class="card2">
          <img src="./assets/11ปลาหมึกผัดไข่เค็ม.jpg" id="foodpicture" />
          <div>
            <h4><b>11ปลาหมึกผัดไข่เค็ม</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/12ยอดฟักแม้วผัดปลาเค็ม.jpg" id="foodpicture" />
          <div>
            <h4><b>12ยอดฟักแม้วผัดปลาเค็ม</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/13แกงส้มไข่ปลาเรียวเซียว.jpg" id="foodpicture" />
          <div>
            <h4><b>13แกงส้มไข่ปลาเรียวเซียว</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
        <div class="card2">
          <img src="./assets/14ปูม้านึ่ง.jpg" id="foodpicture" />
          <div>
            <h4><b>14ปูม้านึ่ง</b></h4>
          </div>
          <p>200 Bant</p>
          <button class="button">
            <img src="./assets/plus.png" id="plus" /> เพิ่ม
          </button>
        </div>
      </section>
      <footer class="footer">By Pornpimon Lakvirote</footer>
</div>

      <div class="login">
  <form>

    <label for="country">E-Mail</label>
    <input type="text" id="lname" name="lastname" placeholder="Your E-Mail">

    <label for="country">Password</label>
    <input type="text" id="lname" name="lastname" placeholder="Password">

    <div class="loginRegister">
    <input type="submit1" value="Register">
    <input type="submit1" value="Log-In">
    </div>
  </form>
</div>
<div class="listbuy">
    <p>ราคารวม</p>
    <input type="submit" value="สั่งอาหาร">
</div> -->


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