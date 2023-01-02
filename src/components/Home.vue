<template>
  <div>
    <Header />
    <h2>Hello {{ name }} this is Home page</h2>
    <table border="1">
      <tr>
        <td>Id</td>
        <td>Name</td>
        <td>Contact</td>
        <td>Address</td>
        <td>Action</td>
      </tr>
      <tr v-for="item in restaurant" :key="item.id">
        <td>
          {{ item.id }}
        </td>
        <td>
          {{ item.name }}
        </td>
        <td>
          {{ item.contact }}
        </td>
        <td>
          {{ item.address }}
        </td>
        <!-- <td><router-link to="/update">update</router-link></td> -->
        <!-- For catch id  -->
        <td><router-link :to="'/update/'+item.id">update</router-link></td>
      </tr>
    </table>
  </div>
</template>
<script>
/* eslint-disable */
import Header from "./Header.vue";
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      name: "",
      restaurant: [],
    };
  },
  components: {
    Header,
  },
  async mounted() {
    let user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name;
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
    let result = await axios.get("http://localhost:3000/restaurant");
    console.warn(result);
    this.restaurant = result.data;
  },
};
</script>
<style lang="css" scoped>
td {
  height: 30px;
  text-align: center;
  font-size: 15px;
  width: 120px;
  padding: 10px 0;
}
td a {
  text-decoration: none;
  font-size: 15px;
}
</style>
