<script>
import { store } from './store'
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue'

export default {
   data() {
      return {
         store,
      }
   },

   methods : {
      searchMovie(searchedTextFilm){
            axios.get("https://api.themoviedb.org/3/movie/550?api_key=08440675644133f8318898097dda140e", {
               params: {
                  query: searchedTextFilm,
                  page: 1,
                  include_adult: false,
               }
         })
         .then((response) => {
            console.log(response.data.results);
            store.searchedMovie = response.data.results
            console.log(store.searchedMovie);
         })
         .catch(function (error) {
            console.log(error);
         })
      },

      searchTvshow(searchedTextFilm){
         axios.get("https://api.themoviedb.org/3/movie/550?api_key=08440675644133f8318898097dda140e", {
               params: {
                  query: searchedTextFilm,
                  page: 1,
                  include_adult: false,
               }
         })
         .then((response) => {
            console.log(response.data.results);
            store.searchedTvshow = response.data.results
            console.log(store.searchedTvshow)
         })
         .catch(function (error) {
            console.log(error);
         });
      }
   },

   components: {
    AppHeader,
    AppMain
  },
}
</script>

<template>

   <section>

      <AppHeader  @searchMovie="[searchMovie(store.searchText), searchTvshow(store.searchText)]"/>

   </section>




</template>

<style lang="scss">

</style>
