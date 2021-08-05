<template>
  <div class="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/add">Add restaurant</router-link>
    <a v-on:click="logout" href="#">Logout</a>
  </div>
</template>

<script>
export default {
  name: "Header",
  methods: {
    logout() {
      localStorage.clear();
      this.$router.push({ name: "LoginPage" });
    },
  },
};
</script>

<style>
.nav {
  background-color: #333;
  overflow: hidden;
}
.nav a {
  color: #f2f2f2f2;
  text-decoration: none;
  float: left;
  padding: 14px 16px;
  font-size: 17px;
  margin-right: 5px;
  text-align: center;
}
.nav a:hover {
  background: #ddd;
  color: #333;
}
</style>
