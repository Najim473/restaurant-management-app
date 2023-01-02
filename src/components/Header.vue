<template>
  <div class="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/add">Add Restaurant</router-link> 
    <a v-on:click="logout">Logout</a>
  </div>
</template>
<script>
/* eslint-disable */
export default {
  name: "Header",
  methods: {
    logout() {
      localStorage.clear();
      this.$router.push({ name: "Login" });
      //   console.warn("Logout");
    },
  },
};
</script>
<style lang="css" scoped>
.nav {
  background: #333;
  font-size: 30px;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  text-align: center;
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 0 16px 0;
}
ul {
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 0 16px 0;
}
.nav a {
  color: #fff;
  margin: 0 12px;
  text-decoration: none;
  padding: 10px;
}
.nav a:hover {
  background: #fff;
  color: #333;
  border-radius: 4px 20px 40px;
}
</style>
