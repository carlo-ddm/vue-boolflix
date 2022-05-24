<template>
  <main>
    <h1>{{titleCards}}</h1>
    <div class="main-wrapper">
      <CardComp v-for="card in items" :key="card.id" :cardData="card"/>
    </div>
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
  .main-wrapper {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
</style>