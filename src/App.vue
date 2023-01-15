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
            query: searchedText,
            page: 1,
            include_adult: false,
         }
         })
         .then((response) => {
            console.log(response.data.results);
            store.searchedMovie = response.data.results
            console.log(store.searchedMovie);
         })
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

      <AppHeader/>

   </section>




</template>

<style lang="scss">

</style>
