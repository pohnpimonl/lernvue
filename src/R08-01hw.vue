<template>
  <div>
    <table>
      <tr>
        <td>{{ xo1 }}</td>
        <td>{{ xo2 }}</td>
        <td>{{ xo3 }}</td>
      </tr>
      <tr>
        <td>{{ xo4 }}</td>
        <td>{{ xo5 }}</td>
        <td>{{ xo6 }}</td>
      </tr>
      <tr>
        <td>{{ xo7 }}</td>
        <td>{{ xo8 }}</td>
        <td>{{ xo9 }}</td>
      </tr>
    </table>
    <br/>
    <table>
      <tr>
        <td><button @click="test1('X')">X</button><button @click="test1('O')">O</button><button @click="test1(' ')" class="dash">O</button></td>
        <td><button @click="test2('X')">X</button><button @click="test2('O')">O</button><button @click="test2(' ')" class="dash">O</button></td>
        <td><button @click="test3('X')">X</button><button @click="test3('O')">O</button><button @click="test3(' ')" class="dash">O</button></td>
      </tr>
      <tr>
        <td><button @click="test4('X')">X</button><button @click="test4('O')">O</button><button @click="test4(' ')" class="dash">O</button></td>
        <td><button @click="test5('X')">X</button><button @click="test5('O')">O</button><button @click="test5(' ')" class="dash">O</button></td>
        <td><button @click="test6('X')">X</button><button @click="test6('O')">O</button><button @click="test6(' ')" class="dash">O</button></td>
      </tr>
      <tr>
        <td><button @click="test7('X')">X</button><button @click="test7('O')">O</button><button @click="test7(' ')" class="dash">O</button></td>
        <td><button @click="test8('X')">X</button><button @click="test8('O')">O</button><button @click="test8(' ')" class="dash">O</button></td>
        <td><button @click="test9('X')">X</button><button @click="test9('O')">O</button><button @click="test9(' ')" class="dash">O</button></td>
      </tr>
      <tr>
        <td colspan="3"><button @click="test10()" class="buttonreset">Reset</button></td>
      </tr>
    </table>
    </div>
</template>
<script>
export default {
  data() {
    return {
      xo1: "",
      xo2: "",
      xo3: "",
      xo4: "",
      xo5: "",
      xo6: "",
      xo7: "",
      xo8: "",
      xo9: "",
    };
  },
  methods: {
    test1(y) {
      this.xo1 = y;
    },
    test2(y) {
      this.xo2 = y;
    },
    test3(y) {
      this.xo3 = y;
    },
    test4(y) {
      this.xo4 = y;
    },
    test5(y) {
      this.xo5 = y;
    },
    test6(y) {
      this.xo6 = y;
    },
    test7(y) {
      this.xo7 = y;
    },
    test8(y) {
      this.xo8 = y;
    },
    test9(y) {
      this.xo9 = y;
    },
    test10(){
      this.xo1 = ' ';
      this.xo2 = ' ';
      this.xo3 = ' ';
      this.xo4 = ' ';
      this.xo5 = ' ';
      this.xo6 = ' ';
      this.xo7 = ' ';
      this.xo8 = ' ';
      this.xo9 = ' ';
    }
  },
};
</script>
<style>
.dash {
  color: #efefef;
}
td{
  width: 100px;
  height: 100px;
  border: 1px solid;
  text-align: center;

}
.buttonreset{
  font-weight: bolder;
  color: white;
  background-color: red;
}
</style>