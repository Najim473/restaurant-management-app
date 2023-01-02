<template>
  <div>
    <Header />
    <h1>Hello user, Welcome to add restaurant Page</h1>
    <form class="add">
      <input type="text" placeholder="Enter Name" />
      <input type="text" placeholder="Enter Address" />
      <input type="text" placeholder="Enter Contact" />
      <button type="button">Add New restaurant</button> 
    </form>
  </div>
</template>
<script>
/* eslint-disable */
import Header from "./Header.vue";
export default {
  name: "Add",
  data(){
    return{
      restaurant:{
      name:"",
      address:"",
      contact:""
    }
    }
  },
  components: {
    Header,
  },
};
</script>
<style lang="css" scoped>

</style>
