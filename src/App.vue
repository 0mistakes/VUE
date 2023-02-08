<script>
  export default {
    data() {
	return {
		name: 'Pudge',
		surn: ' ',
    text: 'page',
		href: 'page.html',
    num: 5,
    num1: 1,
		num2: 2,
		num3: 3,
    arr1: ['x', 'y', 'z'], 
    arr2: [1, 2, 3], 
  }
    }
  }

</script>

<template>
  <div>
		<h1> vue quest </h1>
	</div>
  <br>
  <div> <p> {{ name }} {{ surn }}</p>
  </div>
  <a href="page.html">page</a>
  <p>Квадрат num равен {{num*num}}, сумма num1,num2,num3 равна {{num1+num2+num3}}</p>
</template>

<style >
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