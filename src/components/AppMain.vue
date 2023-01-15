
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
      <div class="film">
         {{ movie.title }} - {{ movie.original_title }} - {{ movie.original_language }} - {{ movie.vote_average }}
      </div>

      <div class="tvShow">
         {{ tvShow.name }} - {{ tvShow.original_name }} - {{ tvShow.original_language }} - {{ tvShow.vote_average }}
      </div>
   </div>
</template>


<style lang="">
   
</style>