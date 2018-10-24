<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    {{ allVideos }}
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import ALL_VIDEOS from './allVideos.gql';
import gql from "graphql-tag";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    allVideos: {
      query: gql`${ALL_VIDEOS}
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
