<template>
  <router-view />
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  padding: 0;
  margin: 0;
}
.logo {
  width: 200px;
  height: 150px;
}
.register input,
.login input,
.add input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  border: 1px solid skyblue;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 30px;
}
.register button,
.login button,
.add button {
  width: 320px;
  height: 40px;
  background: skyblue;
  color: #fff;
  cursor: pointer;
}
</style>
