<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";

export default {
  name: "home",
  components: {
    HelloWorld
  },
  created() {
    axios
      .get("https://localhost:5001/api/values")
      .then(response => {
        // eslint-disable-next-line no-console
        console.log(response);
      })
      .catch(e => {
        this.errors.push(e);
      });
  }
};
</script>
