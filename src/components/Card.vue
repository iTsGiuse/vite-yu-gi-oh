<script>

    export default{
        name: 'Card',
        props: ['carta']
    }

</script>

<template>

    <div class="ms-col">
        <div class="card d-flex justify-content-center align-items-center mb-5" >
            <img :src="carta.card_images[0].image_url" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ carta.name }}</h5>
                <p class="card-text">{{ carta.archetype }}</p>
            </div>
        </div>
    </div>


</template>

<style scoped lang="scss">

    .ms-col{
        width: calc(100% / 5 );

        .card{
            background-color: orange !important;
                    
            .card-title{
                color: white !important;
            }

            .card-text{
                    color: black !important;
            }
        }
    }

</style>