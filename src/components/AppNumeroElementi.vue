<script>

    import { store } from '../store.js';

    export default{
        name: 'AppNumeroElementi',

        data(){
            return{
                store
            };
        },
    }

</script>


<template>

    <div class="black">
        <p>Il numero di carte è: {{ store.carte.length }}</p>
    </div>

</template>
 

<style scoped lang="scss">

    .black{
        background-color: black !important;
        width: 98%;

        p{
            color: white;
            font-size: 23px;
        }
    }

</style>