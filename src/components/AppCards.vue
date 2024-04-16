<script>
    import { store } from '../store.js';
    import Card from './Card.vue';
    import AppSearch from "./AppSearch.vue";

    export default{
        name: 'AppCards',

        components: {
            Card,
            AppSearch,
        },

        data(){
            return {
                store
            };
        },
    }

</script>

<template>

    <div class="container p-5">
        <AppSearch class="mb-4 margin"></AppSearch>
        <div class="container p-5">
            <div class="row flex-wrap">
                <Card v-for="carta in store.carte" :key="carta.id" :carta="carta"></Card> 
            </div>
        </div>
    </div>


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

            .row{
                width: 100% !important;

            }
        }
    }

</style>