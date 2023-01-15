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
