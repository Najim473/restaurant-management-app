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
        <td>
          <router-link :to="'/update/' + item.id">update</router-link>
          <button @click="deleteRestaurant(item.id)">Delete</button>
        </td>
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
  methods: {
    async deleteRestaurant(id) {
      console.log(id);
      let result = await axios.delete("http://localhost:3000/restaurant/" + id);
      console.log(result);
      if (result.status == 200) {
        this.loadData();
      }
    },
    async loadData() {
      let user = localStorage.getItem("user-info");
      this.name = JSON.parse(user).name;
      if (!user) {
        this.$router.push({ name: "SignUp" });
      }
      let result = await axios.get("http://localhost:3000/restaurant");
      console.warn(result);
      this.restaurant = result.data;
    },
  },
  components: {
    Header,
  },
  async mounted(){
    this.loadData();
  }
  // async mounted() {
  //   let user = localStorage.getItem("user-info");
  //   this.name = JSON.parse(user).name;
  //   if (!user) {
  //     this.$router.push({ name: "SignUp" });
  //   }
  //   let result = await axios.get("http://localhost:3000/restaurant");
  //   console.warn(result);
  //   this.restaurant = result.data;
  // },
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
button {
  border: none;
  border-left: 1px solid #333;
  background: none;
  color: red;
  cursor: pointer;
  padding: 5px;
  margin: 5px;
}
</style>
