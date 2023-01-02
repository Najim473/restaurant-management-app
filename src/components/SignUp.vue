<template>
  <div class="logo">
    <img src="../assets/restLogo.png" alt="" />
  </div>
  <h1>Sign Up</h1>
  <div class="register">
    <input type="text" v-model="name" placeholder="Enter Name" />
    <input type="email" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Passwordf" />
    <button type="submit">Sign Up</button>
  </div>
</template>
<script>
export default {
  name: "SignUp",
  data() {
    return {
      name: "",
      email: "",
      password: "",
    };
  },
  methods:{
    signUp(){
      console.log("signUp")
    }
  }
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
  background: skyblue;
  font-size: 15px;
  border: none;
  cursor: pointer;
  color: #fff;
}
</style>
