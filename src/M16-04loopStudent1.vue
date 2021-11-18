<template>
  <div>{{ mstudent() }}</div>
</template>

<script>
export default {
  data() {
    return {
      student: [
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
    };
  },
  methods: {
    mstudent() {
      let i = 0;
      while (i < this.student.length) {
        console.log(this.student[i]);
        i++;
      }
    },
  },
};
</script>

<style>
</style>