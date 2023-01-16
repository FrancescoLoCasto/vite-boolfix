
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
      <div class="card" v-for="movie in store.searchedMovie">
         <h1>
            Film!
         </h1>

         <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.title">
         <h4>
            {{ movie.title }} 
         </h4>
         <h3>
            {{ movie.original_title }}
         </h3>
         <p>Rating Film: {{ movie.vote_average }}</p>
      </div>

      <div class="card" v-for="tvShow in store.searchedTvshow">
         <h1>
            Tv Show!
         </h1>
         <img :src="`https://image.tmdb.org/t/p/w342/${tvShow.poster_path}`" :alt="tvShow.name">
         <h4>
            {{ tvShow.name }}
         </h4>
         <h3>
            {{ tvShow.original_name }}
         </h3>
         <p>Rating TvShow: {{ tvShow.vote_average }}</p>
      </div>
   </div>
</template>


<style lang="scss">

   .container-film{
      display: flex;
      flex-wrap: wrap;
   }


   .card{
   width: 300px;
   text-align: center;
   color: rgb(149, 15, 15);
   padding: 2rem;
   }
</style>