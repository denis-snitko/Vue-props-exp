<template>
  <div id="app">
    <Input v-on:passing-data="getData($event.text, $event.length)" />
    <hr />
    <getText :text="text" />
    <Counter :length="length" />
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
    };
  },
  components: { Input, getText, Counter },
  methods: {
    getData(text, length) {
      this.text = text;
      this.length = length;
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
</style>
