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
    isVisible: false,
    visible: [false, false, false],
    number: 1,
    number_square: "Task 1",
    numero_uno: 0,
    numero_dos: 0,
    sum_number: "Task 2",
    text_uno: "placeholder",
    text_dos: "placeholder",
    fullName: "",
    userName: "",
    userSurname: "",
    userPatronymic: "",
	};
},

  computed: {
      price() {
        return this.cost * this.amount;
      },
    },
  
  methods: {
    square: function () {
      this.number_square = this.number ** 2;
    },
    sum: function () {
      this.sum_number = this.numero_uno + this.numero_dos;
    },
    swap: function () {
      const temp = this.text_uno;
      this.text_uno = this.text_dos;
      this.text_dos = temp;
    },
    split: function () {
      this.userSurname = this.fullName.split(" ")[0];
      this.userName = this.fullName.split(" ")[1];
      this.userPatronymic = this.fullName.split(" ")[2];
    },
  }
};
</script>
<template>
  input type="number" v-model="number" />
  <button @click="square">Square of number</button>
  &nbsp;
  <p>{{ number_square }}</p>
  &nbsp;
  <input type="number" v-model="numero_uno" />
  <input type="number" v-model="numero_dos" />
  <button @click="sum">Summ of numbers</button>
  &nbsp;
  <p>{{ sum_number }}</p>
  &nbsp;
  <input type="text" v-model="text_uno" />
  <input type="text" v-model="text_dos" />
  <button @click="swap">Swap values</button>
  &nbsp;
  <input type="text" v-model="fullName" />
  <button @click="split">Split full name</button>
  <p>Surname = {{ userSurname }}</p>
  <p>Name = {{ userName }}</p>
  <p>Patronymic = {{ userPatronymic }}</p>
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