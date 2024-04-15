<script>
  import AppHeader from './components/AppHeader.vue';
  import AppCards from './components/AppCards.vue';
  import Card from './components/Card.vue';

  export default {
    components: {
      AppHeader,
      AppCards,
      Card
    }
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
