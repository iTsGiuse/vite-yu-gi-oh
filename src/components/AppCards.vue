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

    <div class="container">
        <div class="container p-5">
            <div class="row flex-wrap">
                <Card v-for="carta in store.carte" :key="carta.id" :card="carta"></Card> 
            </div>
        </div>
    </div>


</template>

<style scoped lang="scss">

    .container:nth-child(1){
        width: 1200px !important;
        background-color: orange !important;

        .container:nth-last-child(1){
            width: 800px !important;
            background-color: black !important;

            .row{
                width: 100% !important;

            }
        }
    }

</style>