<template>
  <div class="main">
    <div class="images">
      <div class="image">
        <img :src="imagescolor" />
      </div>
      <div class="selectimage1">
        <label>Select Color :</label>
        <button @click="colorImages('normal')">Normal</button>
        <button @click="colorImages('blue')" class="blue">Blue</button>
        <button @click="colorImages('pink')" class="pink">Pink</button>
        <button @click="colorImages('black')" class="black">Black</button>
      </div>
    </div>
    <div class="images">
      <div class="image">
        {{ pricestel }} Baht
      </div>
      <div class="selectimage2">
        <label>Select Model :</label>
        <button @click="telPrices(500)">Normal</button>
        <button @click="telPrices(450)">Mini</button>
        <button @click="telPrices(750)">Pro</button>
        <button @click="telPrices(900)">Promax</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      imagescolor: " ",
      pricestel: 0,
      images: {
        normal: "https://cf.shopee.co.th/file/11477dbf91bffaac2f8070e8fab169e1",
        blue: "https://cf.shopee.co.th/file/ffd4c8e1f508d728831734c3fe47c1d4",
        pink: "https://cf.shopee.co.th/file/4a745a1c651cecaeeb1c3aa9ff0771da",
        black: "https://cf.shopee.co.th/file/9cca107f9632c1f0bfb244c746150350",
      },
      prices: {
        normal: 500,
        mini: 450,
        pro: 750,
        proMax: 900,
      },
    };
  },
  methods: {
    colorImages(color) {
      if (color == "normal") this.imagescolor = this.images.normal
      else if (color == "blue") this.imagescolor = this.images.blue
      else if (color == "pink") this.imagescolor = this.images.pink
      else this.imagescolor = this.images.black;
    },
    telPrices(price) {
      if (price == 500) this.pricestel = this.prices.normal
      else if (price == 450) this.pricestel = this.prices.mini
      else if (price == 750) this.pricestel = this.prices.pro
      else this.pricestel = this.prices.proMax
    },
  },
};
</script>
<style>
html, body {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
}
.main{
    text-align: center;
}
.images{
    display: flex;
    height: 100%;
}
.image{
    width: 50%;
    font-size: 2cm;
    border: 1px solid;
    
}
.image img{
    width: 380px;
}
.selectimage1{
    padding-top: 4.5cm;
    width: 50%;
    height: 400px;
    border: 1px solid;
}
.selectimage2{
    width: 50%;
    padding-top: 1cm;
    border: 1px solid;
}
.blue{
    color: white;
    background-color: blue;
}
.pink{
    color: white;
    background-color: palevioletred;
}
.black{
    color: white;
    background-color: black;
}
button{
    margin: 0.1cm;
}
</style>