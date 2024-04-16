<script>
  
  import { store } from "./store.js";
	import axios from 'axios';
  import AppHeader from './components/AppHeader.vue';
  import AppCards from './components/AppCards.vue';
  

  export default {
    components: {
      AppHeader,
      AppCards,
    },
    data (){
      store
    },
    methods: {

      getCartaFromApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
          .then(response => {
            store.carte = response.data.data;
          })
        },

      },
    mounted() {
      this.getCartaFromApi();
    }, 
  }
</script>

<template>

  <AppHeader></AppHeader>

  <main>
    <AppCards></AppCards>
  </main>

</template>

<style scoped>

</style>
