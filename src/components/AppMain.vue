
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

   methods: {
      getImagePath(imgFlag){
         if (imgFlag !== 'da' && imgFlag !== 'de' && imgFlag !== 'en' && imgFlag !== 'fr' && imgFlag !== 'hi' && imgFlag !== 'it' && imgFlag !== 'ja' && imgFlag !== 'zh'){
            return new URL(`../assets/img/${imgFlag}.png`, import.meta.url).href;
         }
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
         <p>Rating Movie: <i class="fa-solid fa-star" v-for="n in Math.ceil(movie.vote_average / 2)"></i>
         <i class="fa-regular fa-star" v-for="n in Math.floor(5 - (movie.vote_average / 2))"></i>   
         </p>
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
         <p>Language: <img class="flagImg" :src="getImagePath(movie.original_language)" alt="Non disponibile"></p>
         <p>Rating Tv Shows: <i class="fa-solid fa-star" v-for="n in Math.ceil(tvShow.vote_average / 2)"></i>
         <i class="fa-regular fa-star" v-for="n in Math.floor(5 - (tvShow.vote_average / 2))"></i>   
         </p>
      </div>
   </div>
</template>


<style lang="scss">

   .container-film{
      display: flex;
      flex-wrap: wrap;
      background-color: rgb(63, 63, 63);
   }


   .card{
   width: 300px;
   text-align: center;
   color: rgb(255, 255, 255);
   padding: 2rem;
   }

   .flagImg{
      height: 40px;
   }
</style>