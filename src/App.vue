<script>

  import AppHeader from './components/AppHeader.vue';
  import AppCards from './components/AppCards.vue';
  import { store } from "./store.js";
	import axios from 'axios';

  export default {
    components: {
      AppHeader,
      AppCards,
    },
    methods: {
      getCartaFromApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
          .then(response => {
            store.carte = response.data.data;
          })
          .catch(error => {
            console.error('Si è verificato un errore:', error);
          });
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
