<script>
export default {
    data() {
	return {
    text: 'Initial value',
		name: 'Pudge',
		surn: ' ',
		href: 'page.html',
    cost: 10,
    amount: 5,
    isVisible: false,
    visible: [false, false, false],
    buttonText: ['Show paragraph 1', 'Show paragraph 2', 'Show paragraph 3'],
    isAdmin: true,
    day: new Date().toLocaleString('en-US', { weekday: 'long' }),
    hrefs: [
        {href: '1.html', text: 'text1'},
        {href: '2.html', text: 'text2'},
        {href: '3.html', text: 'text3'},
		],
    products: [
        {
          name: 'product1',
          price: 100,
          quantity: 5
        },
        {
          name: 'product2',
          price: 200,
          quantity: 4
        },
        {
          name: 'product3',
          price: 300,
          quantity: 3
        },
    ],
    items: [1, -2, 3, -4, 5],
	};
},

  computed: {
      price() {
        return this.cost * this.amount;
      },
    },
  
  methods: {
    show() {
      alert(new Date().toLocaleString());
    },
    handleClick() {
      this.clicks++;
      console.log('Button clicked');
    },
    handleClick(event) {
      // Обработчик клика на ссылке
      // Остановить действие по умолчанию (переход по ссылке)
      event.preventDefault();
    },

    getDayOfWeek(num) {
      const daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
      return daysOfWeek[num];
    },
    updateCost() {
      this.cost += 1;
    },

    showDayOfWeek() {
      const currentDay = new Date().getDay();
      alert(`Today is ${this.getDayOfWeek(currentDay)}`);
    },
    changeText1() {
      this.text = 'First value';
    },
    changeText2() {
      this.text = 'Second value';
    },
    changeText2() {
      this.text = 'Second value';
    },
    changeCost() {
      this.cost += 5;
    },
    hideParagraphs() {
      this.showParagraph1 = false;
      this.showParagraph2 = false;
      this.showParagraph3 = false;
    },
    toggleParagraph() {
      this.showParagraph = !this.showParagraph
    },
    square(num) {
      return num ** 2;
    },
  },
  
  created() {
    this.showDayOfWeek();
  },
};
</script>
<template>
  <div>
		<h1> vue quest </h1>
	</div>
  <br>
  <div class="left-side">
    <p> {{ name }} {{ surn }}</p>
  </div>
  <a href="page.html" v-on:click.prevent="handleClick">Page</a>
  <button @mouseenter="show" class="custom-btn btn-12">
    <span>Узнать дату</span>
  </button>
  Задание 1&nbsp;|&nbsp;
  <ul v-for="smh in hrefs">
    <li><a href="{{ smh.href }}">{{ smh.text }}</a></li>
  </ul>
  <br>Задание 2&nbsp;|&nbsp;
  <table v-for="product in products">
    <tr>
      <td>{{ product.name }}</td>
      <td>{{ product.price }}</td>
      <td>{{ product.quantity }}</td>
    </tr>
  </table>
  <p v-for="num in 30">{{ num }}&nbsp;</p>
  <div v-for="item in items">
    <p v-if="item >= 0">{{ item }}&nbsp;</p>
  </div>
</template>
<style >

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