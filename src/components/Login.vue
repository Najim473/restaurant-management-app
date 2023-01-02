<template>
  <h3 :style="{textAlign:'center',fontSize:'30px'}">This is Login page</h3>
  <div class="logo">
    <img src="../assets/restLogo.png" alt="" />
  </div>
  <h1>Login</h1>
  <div class="register">
    <input type="text" v-model="name" placeholder="Enter Name" />
    <input type="email" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Passwordf" />
    <button @click="signUp">Login</button>
    <router-link to="/sign-up">sign-up</router-link>
  </div>
</template>
<script>
export default {
  /* eslint-disable */
  name: "Login",
};
</script>
<style lang="css" scoped>
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
.register {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.register input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 30px;
  border: 1px solid skyblue;
}
.register button {
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
