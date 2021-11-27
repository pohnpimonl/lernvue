<template>
  <div>
    <div class="logo"><img :src="logoimg" /></div>
    <div class="navmenu">
      <button :class="PLogoMenup === 1 ? 'activeMenu' : 'defaultMenu'" @click="to(1)">อาหาร</button>
      <button :class="PLogoMenup === 2 ? 'activeMenu' : 'defaultMenu'" @click="to(2)">สมาชิก</button>
      <button :class="PLogoMenup === 3 ? 'activeMenu' : 'defaultMenu'" @click="to(3)">รายการสั่งซื้อ</button>
      <span v-show="cart.length">{{ cart.length }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['PLogoMenup', 'cart'],
  data() {
    return {
      logoimg: require("../assets/logo.jpg"),
    }
  },
  methods: {
    to(page) {
      this.$emit("menu:chenge", page)
    },
  },
}
</script>

<style>
.logo {
  height: 290px;
  padding: 90px 0 10px;
  text-align: center;
}
.logo img {
  height: 100%;
  border-radius: 40%;
}
.navmenu {
  text-align: center;
}
.navmenu button{
  padding: 14px 20px;
  margin: 8px 8px;
  border: none;
  border-radius: 20px;
}
.navmenu button:hover{
  background-color: crimson;
}
.activeMenu {
  background-color: #9a0606;
  color: white;
}
.defaultMenu {
  background-color: #eeeeee;
  color: #8f8f8f;
  border: none;
}
</style>