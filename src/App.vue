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
  /* text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}

.logo {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: -30px;
}
.logo img {
  width: 100px;
}
h1 {
  text-align: center;
}
.register,
.login, .add {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.register input,
.login input, .add input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 30px;
  border: 1px solid skyblue;
}
.register button,
.login button, .add button {
  width: 320px;
  height: 40px;
  background: rgb(11, 148, 202);
  font-size: 15px;
  border: none;
  cursor: pointer;
  color: #fff;
}
a {
  font-size: 20px;
  text-align: center;
  margin-top: 20px;
}
</style>
