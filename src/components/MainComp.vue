<template>
  <main>
    <h1>{{titleCards}}</h1>

    <CardComp v-for="card in items" :key="card.id" :cardData="card"/>
    <!-- componente card da ciclare -->
    

  </main>
</template>

<script>
import CardComp from './CardComp.vue';
export default {
    name: "MainComp",
    props: {
        items: Array,
        titleCards: String
    },
    components: { CardComp }
}
</script>

<style lang="scss" scoped >

</style>