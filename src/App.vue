<script>
  
  import { store } from "./store.js";
	import axios from 'axios';
  import AppHeader from './components/AppHeader.vue';
  import AppSearch from './components/AppSearch.vue';
  import AppNumeroElementi from './components/AppNumeroElementi.vue';
  import AppCards from './components/AppCards.vue';

  export default {
    
    components: {
      AppHeader,
      AppSearch,
      AppNumeroElementi,
      AppCards
    },
    
    data (){
      return{
        store,
        parametri: {
          num: 20,
          offset: 0
        }
      }
    },
    
    methods: {
      
      getArchetypeFromApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
          .then(response => {
            store.archetype = response.data;
          })
      },

      getCartaFromApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', { params: this.parametri })
          .then(response => {
            store.carte = response.data.data;
          })
      },

      getFilterApi(){
        this.parametri.archetype = store.carteFiltrate;
        
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', { params: this.parametri })
          .then(response => {
            store.carte = response.data.data;
          })
       
      },

      },
      mounted() {
        this.getCartaFromApi();
        this.getArchetypeFromApi();
      }, 
  }
</script>

<template>

  <AppHeader></AppHeader>

  <main>
    <div class="container p-5">
        <AppSearch class="mb-4 margin" @filterCarte="getFilterApi"></AppSearch>
        <div class="container p-5 pt-4">
          <AppNumeroElementi class="p-2"></AppNumeroElementi>
          <AppCards></AppCards>
        </div>
    </div>
  </main>

</template>

<style scoped lang="scss">

  .container:nth-child(1){
    background-color: orange !important;

    .margin{
      margin-left: 5%;
    }

    .container:nth-last-child(1){
        width: 90% !important;
        background-color: white !important;
    }

  }

</style>
