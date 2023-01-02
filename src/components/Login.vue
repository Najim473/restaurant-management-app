<template>
  <div class="logo">
    <img src="../assets/restLogo.png" alt="" />
  </div>
  <h1>Login</h1>
  <div class="login">
    <input type="email" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Passwordf" />
    <button @click="login">Login</button>
    <router-link to="/sign-up">sign-up</router-link>
  </div>
</template>
<script>
import axios from "axios";
export default {
  /* eslint-disable */
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
   async login() {
      let result =await axios.get(
        `http://localhost:3000/user?email=${this.email}&password=${this.password}`
      );
      if(result.status==200 && result.data.length>0){
        localStorage.setItem("user-info",JSON.stringify(result.data[0]))
        this.$router.push({name:"Home"})
      }
      else{
        
      }
      //   console.warn(this.email, this.password);
      console.warn(result);
    },
  },
  mounted(){
    let user = localStorage.getItem('user-info')
    if(user){
        this.$router.push({name:"Home"})
    }
  }
};
</script>
