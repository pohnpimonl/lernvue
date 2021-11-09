<template>
  <div>
      <p>ราคารวม :{{price.sumPrice}}</p>
      <button @click="addPrice(100)">เพิ่ม 100 บาท</button>
      <button @click="addPrice(50)">เพิ่ม 50 บาท</button>
      <button @click="addPrice(20)">เพิ่ม 20 บาท</button>
      <button @click="addPrice(10)">เพิ่ม 10 บาท</button>
      <button @click="addPrice(5)">เพิ่ม 5 บาท</button>
      <button @click="addPrice(2)">เพิ่ม 2 บาท</button>
      <button @click="addPrice(1)">เพิ่ม 1 บาท</button>
      <p v-show="price.sumPrice>50">ราคารวมมากกว่า 50 บาท ส่วนลด 5 บาท</p>
      <p v-show="price.sumPrice>150">ราคารวมมากกว่า 150 บาท ส่วนลด 25 บาท</p>
      <p v-show="price.sumPrice>250">ราคารวมมากกว่า 250 บาท ส่วนลด 50ฦ บาท</p>
  </div>
</template>

<script>
export default {
    data(){
        return{
            price:{
                sumPrice:0,
            },
        }
    },
    methods:{
        addPrice(cost){
            this.price.sumPrice+=cost
        },


}
}
</script>

<style>

</style>