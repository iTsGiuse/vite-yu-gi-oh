<script>

    import { store } from '../store.js';

    export default {
        name: 'AppSearch',
        data(){
            return {
                store
            };
        },
    }

</script>

<template>

    <select> 
        <option value="" selected>Seleziona un Archetype</option>
        <option v-for="tipo in store.archetype" :value=" tipo.archetype_name"> {{ tipo.archetype_name }} </option>
    </select>

</template>


<style scoped lang="scss">

    select{
        padding: 10px;
    }

</style>