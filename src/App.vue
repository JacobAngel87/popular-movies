<template>
  <div id="app">
    <!-- Adding My Header and Card Components-->
    <Header></Header>
    <!-- Binding the tvShows that we revived from the API to a prop in the Card Component -->
    <Card v-bind:shows=tvShows></Card>
  </div>
</template>

<script>
// Importing My Components
import Header from './components/Header.vue'
import Card from './components/Card.vue'
// Importing Axios for the API
import Axios from 'axios';
export default {
  // Name of Vue App
  name: 'App',
  // My Components
  components: {
    Header,
    Card
  },
  // Variables for the App Scope
  data() {
    return {
      APIcall: "https://api.themoviedb.org/3/tv/popular?api_key=7651dcb05e61df0008fe2c9a3fcc7f62&language=en-US&page=1",
      numofTvShows: 4,
      tvShows: []
    }
  },
  // Axios API call that sets the tvShows variable to the desired number of movies reviced from the API
  mounted() {
    Axios.get(this.APIcall)
    .then((response)=>{
      this.tvShows = response.data.results;
      this.tvShows = this.tvShows.splice(0, this.numofTvShows)
    })
    .catch((e)=>{
      console.log(e);
    })
  }
}

</script>

<style>
/* Main Styles */
#app {
  font-family: Avenir, Helvetica, 'Times New Roman', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow-x: hidden;
 background-image: linear-gradient(180deg, lightslategray, lightskyblue);
}
/* Resetting the margin and padding of everything */
* {
  margin: 0;
  padding: 0;
}
</style>
