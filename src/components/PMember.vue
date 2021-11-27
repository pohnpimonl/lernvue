<template>
  <div class="formlogina">
    <div v-if="tab === 1" class="formloginb">
      <form>
        <label for="email">อีเมลล์</label>
        <input type="email" placeholder="Your email.." />

        <label for="password">รหัสผ่าน</label>
        <input type="password" placeholder="Your password.." />
        <div class="formloginc">
          <button type="button" @click="to(1)">+ สมัครสมาชิก</button>
          <button type="submit">เข้าสู่ระบบ</button>
        </div>
      </form>
    </div>
    <div v-if="tab === 2"><p-register></div>
  </div>
</template>

<script>
import PRegister from './PRegister.vue'
export default {
  components: {
    PRegister,
  },
  data(){
    return{
      tab:1,
    }
  }
}
</script>

<style>
.formlogina {
  margin-top: 20px;
}
.formloginb {
  width: 560px;
  margin-left: auto;
  margin-right: auto;
  padding: 25px 50px;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 20px;
}
input[type="email"],
[type="password"] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
label {
  margin-top: 20px;
  margin-left: 12px;
}
.formloginc {
  display: grid;
  grid-template-columns: 50% 50%;
  grid-column-gap: 10px;
}
.formloginb button {
  background-color: #9a0606;
  color: white;
  padding: 14px 20px;
  margin: 20px 0;
  border: none;
  border-radius: 20px;
}
.formloginb button:hover {
  background-color: crimson;
}
</style>