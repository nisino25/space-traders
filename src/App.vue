<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import LOCAL_TOKEN from "./const/token.js"
function getToken() {
  return (
      LOCAL_TOKEN ||
      process.env.VUE_APP_SPACETRADERS_TOKEN ||
      localStorage.getItem("spacetraders_token")
  )
}

export default {
  name: 'App',
  mounted() {
    console.log("Token:", getToken());
  },

  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
