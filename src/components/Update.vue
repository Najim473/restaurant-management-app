<template>
  <div>
    <Header />
    <h1>Hello user, Welcome to update restaurant Page</h1>
    <form class="update">
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
      <button type="button" @click="UpdateRestaurant">Update Restaurant</button>
    </form>
  </div>
</template>
<script>
/* eslint-disable */
import axios from "axios";
import Header from "./Header.vue";
export default {
  name: "Update",
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
    async UpdateRestaurant() {
      console.log("Updated", this.restaurant);
      const result = await axios.put(
        "http://localhost:3000/restaurant/" + this.$route.params.id,
        {
          name: this.restaurant.name,
          address: this.restaurant.address,
          contact: this.restaurant.contact,
        }
      );
      if(result.status==200){
        this.$router.push({name:"Home"})
      }
    },
  },
  async mounted() {
    let user = localStorage.getItem("user-info");
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
    const result = await axios.get(
      "http://localhost:3000/restaurant/" + this.$route.params.id
    );
    console.log(result);
    // console.log(this.$route.params.id)
    this.restaurant = result.data;
  },
};
</script>
<style lang="css" scoped></style>
