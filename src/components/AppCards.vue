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

    <div class="container p-5">
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

        .container:nth-last-child(1){
            width: 90% !important;
            background-color: white !important;

            .row{
                width: 100% !important;

            }
        }
    }

</style>