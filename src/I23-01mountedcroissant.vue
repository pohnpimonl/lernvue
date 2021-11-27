<template>
  <div>
      <div>Do you love croissant?</div>
      <div v-show="show">Well...</div>
      <div v-show="!show">Yes I love croissant</div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      show:true,
    }
  },
  beforeCreate(){
    console.log('beforeCreate',this.show)
  },
  created(){
    //เอา settimeout ไว้ตรงนี้ก็ได้ แต่เอาไว้ตรง mounted ดีกว่า นับเวลาตั้งแต่สร้าง
    console.log('created',this.show)
  },
  beforeMount(){
    console.log('beforemount',this.show,this.$el)
  },
  mounted(){
    console.log('mounted',this.show,this.$el)
    //นับเวลาตั้งแต่ คอมโพแนน ผูกกับ วิวแล้ว
    //ให้เขียนแบบลัดเท่านั้น ถ้าเขียนเต็ม
    setTimeout(()=>{
      this.show = false
    },3000)
  },
}
</script>

<style>

</style>