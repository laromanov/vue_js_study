<template>
  <div id="app">
    <ul>
      <h1>Name: {{persone.name}}</h1>
      <h1>Age: {{persone.age}}</h1>
      <h1>Count: {{count}}</h1>
    </ul>
    <button @click="increaseCount">increase count</button><br> 
    <button @click="reduceCount">reduce count</button><br>
    <button @click="changeName">change name</button><br><br><br><br><br>

    <p>{{ messageHandler() }}</p><br><br><br><br><br>

    <ul>
      <li> number 1 {{num1}}</li>
      <li> number 2 {{num2}}</li>
      <li> total {{total}}</li>
      <li> method {{addNumber1}}</li>
      <li> method {{addNumber2}}</li>
    </ul>
    <button @click="num1++">add num 1</button>
    <button @click="num2++">add num 2</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      message: 'Hello World',
      total: 20,
      num1: 0,
      num2: 0,
      persone: {
        name: "Mario",
        age: 33
      },
      count: 0
    };
  },
  computed: {
    addNumber1() {
      console.log(1);
      return this.num1 + this.total
    },
    addNumber2() {
      console.log(2);
      return this.num2 + this.total
    }
  },
  methods: {
    increaseCount() {
      this.count++;
    },
    reduceCount() {
      this.count--;
    },
    changeName() {
      this.persone.name = "Boris";
      if (this.persone.name == "Boris") {
        this.alertHandler();
      }
    },
    alertHandler() {
      alert('The name was changed: ', this.persone.name);
    },
    messageHandler() {
      return this.message.split('').reverse().join('')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
