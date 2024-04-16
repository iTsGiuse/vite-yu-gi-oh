<script>
    import { store } from '../store.js';
    import Card from './Card.vue';

    export default{
        name: 'AppCards',

        components: {
            Card,
        },

        data(){
            return {
                store
            };
        },
    }

</script>

<template>

    <div class="row flex-wrap">
        <Card v-for="carta in store.carte" :key="carta.id" :carta="carta"></Card> 
    </div>


</template>

<style scoped lang="scss">

    .row{
        width: 100% !important;
    }
    
</style>