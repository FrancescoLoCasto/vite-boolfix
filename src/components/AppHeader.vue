
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
      Boolfix
   </h1>

   <input type="text" v-model="store.searchText" @keyup.enter="$emit('searchMovie')">
   <button @click="$emit('searchMovie')">Search Film</button>
</div>
</template>


<style lang="scss">
   
</style>