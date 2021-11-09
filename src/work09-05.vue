<template>
  <div>
      <p>ราคารวม :{{price.sumPrice}}</p>
      <button @click="addPrice(100)">เพิ่ม 100 บาท</button>
      <button @click="addPrice(50)">เพิ่ม 50 บาท</button>
      <button @click="addPrice(20)">เพิ่ม 20 บาท</button>
      <button @click="addPrice(10)">เพิ่ม 10 บาท</button>
      <p v-if="(price.count===5)&&(price.sumPrice>50)">ซื้อ 5 ชิ้น ราคารวมมากกว่า 50 บาท ส่วนลด 5 บาท</p>
      <p v-if="(price.count===10)&&(price.sumPrice>150)">ซื้อ 10 ชิ้นราคารวมมากกว่า 150 บาท ส่วนลด 25 บาท</p>
      <p v-if="(price.count===15)&&(price.sumPrice>250)">ซื้อ 15 ชิ้น ราคารวมมากกว่า 250 บาท ส่วนลด 50 บาท</p>
      <p v-if="(price.count===25)||(price.sumPrice>750)">ซื้อ 25 ชิ้น ราคารวมมากกว่า 750 บาท ส่วนลด 100 บาท</p>
  </div>
</template>

<script>
export default {
    data(){
        return{
            price:{
                sumPrice:0,
                count:0,
            },
        }
    },
    methods:{
        addPrice(cost){
            this.price.count++
            this.price.sumPrice+=cost
        },


}
}
</script>

<style>

</style>