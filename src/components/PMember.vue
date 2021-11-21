<template>
  <div class="formlogina">
    <div class="formloginb">
      <form>
        <div class="formloginc">
          <div>อีเมลล์</div>
          <input type="email" />
          <div>รหัสผ่าน</div>
          <input type="password" />
        </div>
        <div class="buttonl">
          <button type="button">+ สมัครสมาชิก</button>
          <button type="submit">เข้าสู่ระบบ</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  
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
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 20px;
}
.formloginc {
  display: block;
  padding: 20px;
}
.formloginc div {
  margin: 20px 0;
}
.formloginc input {
  width: 100%;
}
.buttonl {
  display: grid;
  grid-template-columns: 50% 50%;
}
.buttonl button {
  margin: 10px;
}
</style>