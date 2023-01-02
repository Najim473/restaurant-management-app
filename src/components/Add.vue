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
  methods:{
    addRestaurant(){
console.log('restaurant', this.restaurant) 
    }
  }
};
</script>
<style lang="css" scoped></style>
