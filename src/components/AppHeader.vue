
<script>
import { store } from '../store'


export default {
   name: 'AppHeader',
   data() {
      return {
         store,
      }
   },
}
</script>


<template lang="">
<div class="container-header">
   <h1>
      Boolflix
   </h1>

   <input type="text" v-model="store.searchText" @keyup.enter="$emit('searchMovie')">
   <button @click="$emit('searchMovie')">Search Film</button>
</div>
</template>


<style lang="scss">
   .container-header{
      height: 70px;
      background-color: black;
      color: red;
      display: flex;
      justify-content: space-around;

      h1{
         margin-right: 5rem;
         margin-left: 5rem;

      }
      
      input{
         height: 1.5rem;
         margin-top: 1rem;
         border-radius: 1rem;
      }

      button{
         height: 1.5rem;
         margin-left: 1rem;
         margin-top: 1rem;
         border: 0;
      }
   }
</style>