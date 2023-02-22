<script>
export default {
    data() {
	return {
    isValid: true,
    isDisabled: true,
    text: 'Initial value',
		name: 'Pudge',
		surn: ' ',
		href: 'page.html',
    cost: 10,
    amount: 5,
    dayWeek: "Task 1",
    dayWeekOptions: [
      "Monday",
      "Tuesday",
      "Wednesday",
      "Thursday",
      "Friday",
      "Saturday",
      "Sunday",
    ],
    dayYear: "",
    dayYearOptions: [
        1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20,
        21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31,
    ],
    monthYear: "",
    monthYearOptions: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
    yearYear: "",
    yearYearOptions: [
        2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012,
        2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 2000,
    ],
    };
  },
  computed: {
      price() {
        return this.cost * this.amount;
      },
    },
  
  methods: {
    todayDate: function () {
      var today = new Date();
      this.dayYear = String(today.getDate());
      this.monthYear = String(today.getMonth() + 1);
      this.yearYear = today.getFullYear();
    },
  }
};
</script>
<template>
  &nbsp;
  <p>{{ selected }}</p>
  <select v-model="dayWeek">
    <option v-for="option in dayWeekOptions">{{ option }}</option>
  </select>
  &nbsp;
  {{ dayWeek }}
  &nbsp;

  <select v-model="dayYear">
    <option v-for="option in dayYearOptions">{{ option }}</option>
  </select>
  <select v-model="monthYear">
    <option v-for="option in monthYearOptions">{{ option }}</option>
  </select>
  <select v-model="yearYear">
    <option v-for="option in yearYearOptions">{{ option }}</option>
  </select>
  &nbsp;
  <button @click="todayDate">Today's date</button>
</template>
<style >
.active {
  border: 5px solid red;
}
.valid {
  color: green;
}
p.hidden {
  display: none;
}
done {
  border: 5px solid red;
}
.selected {
  color: green;
  font-size: 10em;
}
.custom-btn {
  width: 130px;
  height: 40px;
  color: #fff;
  border-radius: 10px;
  padding: 10px 25px;
  font-family: 'Lato', sans-serif;
  font-weight: 500;
  background: transparent;
  cursor: pointer;
  transition: all 0.3s ease;
  position: relative;
  display: inline-block;
   box-shadow:inset 2px 2px 2px 0px rgba(255,255,255,.5),
   7px 7px 20px 0px rgba(0,0,0,.1),
   4px 4px 5px 0px rgba(0,0,0,.1);
  outline: none;
}
.btn-13 {
  background-color: #89d8d3;
background-image: linear-gradient(315deg, #89d8d3 0%, #03c8a8 74%);
  border: none;
  z-index: 1;
}
.btn-13:after {
  position: absolute;
  content: "";
  width: 100%;
  height: 0;
  bottom: 0;
  left: 0;
  z-index: -1;
  border-radius: 5px;
   background-color: #4dccc6;
background-image: linear-gradient(315deg, #4dccc6 0%, #96e4df 74%);
  box-shadow:
   -7px -7px 20px 0px #fff9,
   -4px -4px 5px 0px #fff9,
   7px 7px 20px 0px #0002,
   4px 4px 5px 0px #0001;
  transition: all 0.3s ease;
}
.btn-13:hover {
  color: #fff;
}
.btn-13:hover:after {
  top: 0;
  height: 100%;
}
.btn-13:active {
  top: 2px;
}

header {
  line-height: 2.5;
}
p {
  line-height: 2.5;
  font-size: large;
  letter-spacing: 2px;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  color: white;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
  .logo {
    margin: 0 2rem 0 0;
  }
  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>