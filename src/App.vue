<template>
  <div id="app">
    <input type="text" v-model="itemsCount">
    <p>Change the value to <b>3</b> and then return back to <b>2</b></p>
    <p>And you will see an error in console</p>
    <hr>
    {{ allVideos }}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import gql from 'graphql-tag';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      itemsCount: 2,
    };
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    allVideos: {
      query: gql`query allVideos($items: Int!) {
        allVideos(first: $items) {
          id
        }
      }`,
      variables() {
        return {
          items: +this.itemsCount,
        };
      },
    },
  },
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
