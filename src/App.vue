<script>
export default {
    data() {
	return {
    developers: [
        {
          id: 1,
          name: "Bebr",
          salary: 100,
          age: 30,
          isEdit: false,
        },
        {
          id: 2,
          name: "Bebroid",
          salary: 200,
          age: 40,
          isEdit: false,
        },
        {
          id: 3,
          name: "Diand",
          salary: 300,
          age: 50,
          isEdit: false,
        },
      ],
    };
  },
  computed: {
      price() {
        return this.cost * this.amount;
      },
    },
  
  methods: {
    removeItem: function (id) {
      this.developers = this.developers.filter((developer) => {
        return developer.id !== id;
      });
    },
    edit: function (developer) {
      developer.isEdit = true;
    },
    save: function (developer) {
      developer.isEdit = false;
    },
  }
};
</script>
<template>
   <table>
    <tr>
      <th>ID</th>
      <th>Имя</th>
      <th>Зарплата</th>
      <th>Возраст</th>
    </tr>
    <tr v-for="developer in developers">
      <template v-if="!developer.isEdit">
        <td>{{ developer.id }}</td>
        <td>{{ developer.name }}</td>
        <td>{{ developer.salary }}</td>
        <td>{{ developer.age }}</td>
        <td><button @click="removeItem(developer.id)">remove</button></td>
        <td><button @click="edit(developer)">edit</button></td>
      </template>
      <template v-else>
        <td><input v-model="developer.id" /></td>
        <td><input v-model="developer.name" /></td>
        <td><input v-model="developer.salary" /></td>
        <td><input v-model="developer.age" /></td>
        <td><button @click="save(developer)">save</button></td>
      </template>
    </tr>
  </table>
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