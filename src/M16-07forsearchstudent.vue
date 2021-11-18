<template>
  <div>
    <input type="text" v-model="searchId">
    <div>
      {{ searchStatus }}
    </div>
    {{ nested() }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchId:null,
      searchStatus:'',
      students: [
        {
          id: "111",
          name: "มานะ",
          scores: [96, 91, 25, 72, 64, 56, 11, 50, 68, 92],
        },
        {
          id: "222",
          name: "มานี",
          scores: [81, 15, 49, 16, 13, 97, 26, 47, 78, 45],
        },
        {
          id: "333",
          name: "ปิติ",
          scores: [97, 15, 53, 47, 88, 69, 79, 12, 46, 18],
        },
        {
          id: "444",
          name: "ชูใจ",
          scores: [59, 24, 62, 85, 95, 45, 69, 55, 57, 8],
        },
      ],
    }
  },
  watch:{
    searchId(value){
      const student = this.find(value)
      if(student){
        let sum=0
        for(let i=0;i<student.scores.length;i++){
          sum+=student.scores[i]
        }
        this.searchStatus=sum/student.scores.length
      }else{
        this.searchStatus='Not Found..'
      }
    },
  },
  methods: {
    find(id){
      for(let i=0;i<this.students.length;i++){
        const student = this.students[i]
        if(student.id===id){
          return student
        }
      }
      return null
    },
    nested() {
      for (let i = 0;i < this.students.length;i++) {
          const student = this.students[i]
          let sum=0
          for(let j=0;j<student.scores.length;j++){
              sum+=student.scores[j]
          }
          console.log(`student: ${student.name} average: ${sum/student.scores.length}`)
      }
    },
  },
}
</script>

<style>
</style>