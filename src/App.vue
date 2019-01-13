<template>
  <div id="app"><User /></div>
</template>

<script>
import User from "./components/User";

export default {
  name: "App",
  components: {
    User
  }
};
</script>

<style>
.user {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
