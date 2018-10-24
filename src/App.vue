<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    {{ allVideos }}
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import gql from "graphql-tag";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    allVideos: {
      query: gql`query {
        allVideos(first: 2) {
          id
        }
      }`
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
