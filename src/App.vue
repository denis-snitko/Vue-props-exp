<template>
  <div id="app">
    <Input v-on:passing-data="getData($event.text, $event.length)" />
    <hr />
    <getText :text="text" />
    <Counter :length="length" />
    <ul>
      <li v-for="name in filtering" :key="name.id">
        <strong>{{ name.name }}</strong> - (id -{{ name.id }})
      </li>
    </ul>
  </div>
</template>

<script>
import Input from "./components/Input";
import getText from "./components/getText";
import Counter from "./components/Counter";

export default {
  data() {
    return {
      text: "",
      length: 0,
      names: [
        { id: this.generateID(), name: "Денис" },
        { id: this.generateID(), name: "Олег" },
        { id: this.generateID(), name: "Татьяна" },
        { id: this.generateID(), name: "Маргарита" },
        { id: this.generateID(), name: "Света" },
        { id: this.generateID(), name: "Дмитрий" },
      ],
    };
  },
  components: { Input, getText, Counter },
  methods: {
    getData(text, length) {
      this.text = text;
      this.length = length;
    },
    generateID() {
      return (Math.random() * 1000000).toFixed();
    },
  },
  computed: {
    filtering() {
      return this.names.filter((item) =>
        item.name.toLowerCase().includes(this.text.toLowerCase())
      );
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style: none;
}
</style>
