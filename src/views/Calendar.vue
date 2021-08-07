<template>
  <div class="home">
    <div
      class="all"
      :class="{
        january: january,
        february: february,
        march: march,
        april: april,
        may: may,
        june: june,
        july: july,
        august: august,
        september: september,
        october: october,
        november: november,
        december: december,
      }"
    >
      <div class="box">
        <h1>{{ date }}</h1>
        <h3>{{ Day }}</h3>
      </div>
      <table>
        <tr>
          <td :class="{ today: a }" class="day">1</td>
          <td :class="{ today: b }" class="day">2</td>
          <td :class="{ today: c }" class="day">3</td>
          <td :class="{ today: d }" class="day">4</td>
          <td :class="{ today: e }" class="day">5</td>
          <td :class="{ today: f }" class="day">6</td>
        </tr>
        <tr>
          <td :class="{ today: g }" class="day">7</td>
          <td :class="{ today: h }" class="day">8</td>
          <td :class="{ today: i }" class="day">9</td>
          <td :class="{ today: j }" class="day">10</td>
          <td :class="{ today: k }" class="day">11</td>
          <td :class="{ today: l }" class="day">12</td>
        </tr>
        <tr>
          <td :class="{ today: m }" class="day">13</td>
          <td :class="{ today: n }" class="day">14</td>
          <td :class="{ today: o }" class="day">15</td>
          <td :class="{ today: p }" class="day">16</td>
          <td :class="{ today: q }" class="day">17</td>
          <td :class="{ today: r }" class="day">18</td>
        </tr>
        <tr>
          <td :class="{ today: s }" class="day">20</td>
          <td :class="{ today: t }" class="day">21</td>
          <td :class="{ today: u }" class="day">22</td>
          <td :class="{ today: v }" class="day">23</td>
          <td :class="{ today: w }" class="day">24</td>
          <td :class="{ today: x }" class="day">25</td>
        </tr>
        <tr>
          <td :class="{ today: y }" class="day">26</td>
          <td :class="{ today: z }" class="day">27</td>
          <td :class="{ today: aa }" class="day">28</td>
          <td :class="{ today: ab }" v-if="feb" class="day">29</td>
          <td :class="{ today: ac }" v-if="thirty" class="day">30</td>
          <td :class="{ today: ad }" v-if="thirtyOne" class="day">31</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import { fstat } from "fs";
export default {
  name: "Home",
  components: {},
  data() {
    var d = new Date();
    var day = d.getDay();
    var month = d.getMonth();
    var year = d.getFullYear();
    var thirty = false;
    var thirtyOne = false;
    var feb = true;
    var months = [
      "January", // 1 31
      "February", // 2 28
      "March", // 3
      "April", // 4
      "May", // 5
      "June", // 6
      "July", // 7
      "August", // 8
      "September", // 9
      "October", // 10
      "November", // 11
      "December", // 12
    ];
    var days = [
      "Sunday",
      "Monday",
      "Tuesday",
      "Wednesday",
      "Thursday",
      "Friday",
      "Saturday",
    ];
    var s = ", ";
    var date = day + 1 + s + months[month] + " " + year;
    var Day = days[day];

    return {
      date,
      Day,
      day,
      thirty,
      thirtyOne,
      feb,
      month,
      a: false,
      b: false,
      c: false,
      d: false,
      e: false,
      f: false,
      g: false,
      h: false,
      i: false,
      j: false,
      k: false,
      l: false,
      m: false,
      n: false,
      o: false,
      p: false,
      q: false,
      r: false,
      s: false,
      t: false,
      u: false,
      v: false,
      w: false,
      x: false,
      y: false,
      z: false,
      aa: false,
      ab: false,
      ac: false,
      ad: false,
      ae: false,
      af: false,
      twentyseven: false,
      twentyeight: false,
      twentynine: false,
      thirty: false,
      thirtyone: false,
      january: false,
      february: false,
      march: false,
      april: false,
      may: false,
      june: false,
      july: false,
      august: false,
      september: false,
      october: false,
      november: false,
      december: false,
    };
  },
  methods: {
    getMonth() {
      if (this.month === 0 || 1 || 3 || 7 || 8 || 10 || 12) {
        this.thirtyOne = true;
        console.log("31 days is " + this.thirtyOne);
      }
      if (this.month == 2 || 4 || 6 || 9 || 11 || 13) {
        this.thirtyOne = true;
      } else if (this.month == 1) {
        this.feb = true;
        this.thirtyOne = false;
        this.thirty = false;
        console.log("It's February!!!");
      }
      // day number class values a-z + aa-af
      if (this.day == 0) {
        this.a = true;
      } else {
        this.b = false;
      }
      if (this.day == 1) {
        this.b = true;
      } else {
        this.b = false;
      }
      if (this.day == 2) {
        this.c = true;
      } else {
        this.c = false;
      }
      if (this.day == 3) {
        this.d = true;
      } else {
        this.d = false;
      }
      if (this.day == 4) {
        this.e = true;
      } else {
        this.e = false;
      }
      if (this.day == 5) {
        this.f = true;
      } else {
        this.f = false;
      }
      if (this.day == 6) {
        this.g = true;
      } else {
        this.g = false;
      }
      if (this.day == 7) {
        this.h = true;
      } else {
        this.h = false;
      }
      if (this.day == 8) {
        this.i = true;
      } else {
        this.i = false;
      }
      if (this.day == 9) {
        this.j = true;
      } else {
        this.j = false;
      }
      if (this.day == 10) {
        this.k = true;
      } else {
        this.k = false;
      }
      if (this.day == 11) {
        this.l = true;
      } else {
        this.l = false;
      }
      if (this.day == 12) {
        this.m = true;
      } else {
        this.m = false;
      }
      if (this.day == 13) {
        this.n = true;
      } else {
        this.n = false;
      }
      if (this.day == 14) {
        this.o = true;
      } else {
        this.o = false;
      }
      if (this.day == 15) {
        this.p = true;
      } else {
        this.p = false;
      }
      if (this.day == 16) {
        this.q = true;
      } else {
        this.q = false;
      }
      if (this.day == 17) {
        this.r = true;
      } else {
        this.r = false;
      }
      if (this.day == 18) {
        this.s = true;
      } else {
        this.s = false;
      }
      if (this.day == 19) {
        this.t = true;
      } else {
        this.t = false;
      }
      if (this.day == 20) {
        this.u = true;
      } else {
        this.u = false;
      }
      if (this.day == 21) {
        this.v = true;
      } else {
        this.v = false;
      }
      if (this.day == 22) {
        this.w = true;
      } else {
        this.w = false;
      }
      if (this.day == 23) {
        this.x = true;
      } else {
        this.x = false;
      }
      if (this.day == 24) {
        this.y = true;
      } else {
        this.y = false;
      }
      if (this.day == 25) {
        this.z = true;
      } else {
        this.z = false;
      }
      if (this.day == 26) {
        this.aa = true;
      } else {
        this.aa = false;
      }
      if (this.day == 27) {
        this.ab = true;
      } else {
        this.ab = false;
      }
      if (this.day == 28) {
        this.ac = true;
      } else {
        this.ad = false;
      }
      if (this.day == 29) {
        this.ad = true;
      } else {
        this.ad = false;
      }
      if (this.day == 30) {
        this.ae = true;
      } else {
        this.ae = false;
      }
      if (this.day == 31) {
        this.af = true;
      } else {
        this.af = false;
      }
      // month class designation
      if (this.month == 0) {
        this.january = true;
      } else {
        this.january = false;
      }
      if (this.month == 1) {
        this.february = true;
      } else {
        this.february = false;
      }
      if (this.month == 2) {
        this.march = true;
      } else {
        this.march = false;
      }
      if (this.month == 3) {
        this.april = true;
      } else {
        this.april = false;
      }
      if (this.month == 4) {
        this.may = true;
      } else {
        this.may = false;
      }
      if (this.month == 5) {
        this.june = true;
      } else {
        this.june = false;
      }
      if (this.month == 6) {
        this.july = true;
      } else {
        this.july = false;
      }
      if (this.month == 7) {
        this.august = true;
        console.log("aug", this.august);
      } else {
        this.august = false;
        console.log("x");
      }
      if (this.month == 8) {
        this.september = true;
      } else {
        this.september = false;
      }
      if (this.month == 9) {
        this.october = true;
      } else {
        this.october = false;
      }
      if (this.month == 10) {
        this.november = true;
      } else {
        this.november = false;
      }
      if (this.month == 11) {
        this.december = true;
      } else {
        this.december = false;
      }
    },
  },
  created() {
    this.getMonth();
    console.log(this.day, "day");
  },
};
</script>

<style scoped>
h3,
h1 {
  margin: 0;
}
table {
  margin-left: auto;
  margin-right: auto;
}
td {
  height: 30px;
  width: 30px;
  background: wheat;
  border: 2px solid rgb(170, 170, 170);
}
.today {
  color: gold;
  background: grey;
  font-size: 1.5em;
  font-weight: 600;
}
.home {
  position: relative;
}
.january {
  background: rgb(166, 166, 255);
}
.february {
  background: pink;
}
.march {
  background: whitesmoke;
}
.april {
  background: violet;
}
.may {
  background: purple;
}
.june {
  background: orangered;
}
.july {
  background-image: linear-gradient(red, white, blue);
}
.august {
  background: mediumvioletred;
}
.september {
  background: brown;
}
.october {
  background: orange;
}
.november {
  background: rgb(81, 81, 122);
}
.december {
  background: gainsboro;
}
.all {
  height: 100vh;
}
</style>
