<template>
  <p>This is Home page</p>
</template>
<script>
/* eslint-disable */
export default {
  name: "Home",
  mounted() {
    let user = localStorage.getItem("user-info");
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
  }
};
</script>
<style>
p {
  background: #000;
  color: #fff;
  font-size: 30px;
  padding: 50px;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  text-align: center;
}
</style>
