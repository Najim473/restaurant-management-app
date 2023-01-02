<template>
  <div>
    <Header />
    <h1>Hello user, Welcome to add restaurant Page</h1>
    <form class="add">
      <input type="text" placeholder="Enter Name" v-model="restaurant.name" />
      <input
        type="text"
        placeholder="Enter Address"
        v-model="restaurant.address"
      />
      <input
        type="text"
        placeholder="Enter Contact"
        v-model="restaurant.contact"
      />
      <button type="button" @click="addRestaurant">Add New restaurant</button>
    </form>
  </div>
</template>
<script>
/* eslint-disable */
import Header from "./Header.vue";
import axios from "axios";
export default {
  name: "Add",
  data() {
    return {
      restaurant: {
        name: "",
        address: "",
        contact: "",
      },
    };
  },
  components: {
    Header,
  },
  methods: {
    async addRestaurant() {
      console.log("restaurant", this.restaurant);
      const result = await axios.post("http://localhost:3000/restaurant", {
        name: this.restaurant.name,
        contact: this.restaurant.contact,
        address: this.restaurant.address,
      });
     if(result.status==201){
      this.$router.push({name:"Home"})
     }
     else if(result.status!==201){
      alert('Something is wrong')
     }
      console.log("result", result);
    },
  },
};
</script>
<style lang="css" scoped></style>
