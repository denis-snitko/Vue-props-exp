<template>
  <div>
    <input type="text" @keyup="getData($event.target.value)" />
  </div>
</template>

<script>
export default {
  methods: {
    getData(event) {
      this.$emit("passing-data", { length: event.length, text: event });
    },
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
