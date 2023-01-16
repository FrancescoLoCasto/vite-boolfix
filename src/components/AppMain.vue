
<script>

import { store } from '../store'
import "/node_modules/flag-icons/css/flag-icons.min.css";


export default {
   name: 'AppMain',
   data() {
      return {
         store,
      }
   },
}
</script>

<template lang="">
   <div class="container-film">
      <div class="film" v-for="movie in store.searchedMovie">
         <h1>
            Film!
         </h1>
         <h3>
            {{ movie.title }} 
         </h3>
         <h4>
            {{ movie.original_title }}
         </h4>
         <p>Rating Film: {{ movie.vote_average }}</p>
      </div>

      <div class="tvShow" v-for="tvShow in store.searchedTvshow">
         <h1>
            Tv Show!
         </h1>
         <h3>
            {{ tvShow.name }}
         </h3>
         <h4>
            {{ tvShow.original_name }}
         </h4>
         <p>Rating TvShow: {{ tvShow.vote_average }}</p>
      </div>
   </div>
</template>


<style lang="">
   
</style>