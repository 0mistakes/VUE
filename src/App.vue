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
    obj: {
        hidden: true,
      },
    
	};
},

  computed: {
      price() {
        return this.cost * this.amount;
      },
    },
  
  methods: {
    setDone: function () {
      this.obj.hidden = !this.obj.hidden;
    },
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
    add: function() {
		  this.arr.push('b');
  },
    delFirst: function() {
      this.arr.shift();
  },
    delLast: function() {
      this.arr.pop();
  },
    delSecondToLast: function() {
      this.arr.splice(-2, 1);
  },
    sortArr: function() {
      this.arr.sort();
  },
    reverseOrder: function() {
      this.arr.reverse();
  }
  },
  
  created() {
    this.showDayOfWeek();
  },
  add: function() {
		  this.arr.push('b');
  },
    delFirst: function() {
      this.arr.shift();
  },
    delLast: function() {
      this.arr.pop();
  },
    delSecondToLast: function() {
      this.arr.splice(-2, 1);
  },
    sortArr: function() {
      this.arr.sort();
  },
    reverseOrder: function() {
      this.arr.reverse();
  }
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
  <p :style="{ color: 'green', background: 'yellow', fontSize: '30px' }">
    Task 1
  </p>
  &nbsp; &nbsp; &nbsp;
  <p :style="{ fontWeight: 'bold', fontStyle: 'italic', fontSize: '30px' }">
    Task 2
  </p>
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