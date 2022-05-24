<template>
  <main>
    <div class="container">

    <div>
      <CardComp v-for="(movie, index) in arrayMovie" :key="`movie_${index}`" :spettacolo="movie"/>
    </div>
    <div>
       <CardComp v-for="(show, index) in arrayTvShows" :key="`show_${index}`" :spettacolo="show" />
    </div>

    </div>
  </main>
</template>

<script>
import CardComp from './CardComp.vue';
export default {
    name: "MainComp",
    components: { CardComp },

    props: {
      arrayMovie: Array,
      arrayTvShows: Array
    }
}
</script>

<style lang="scss" scoped>
// importo mixines
@import '../assets/styles/mixines';

main {
  @include d-flex-jcen-ac;
  width: 100%;
}
</style>