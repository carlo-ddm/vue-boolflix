<template>
  <main>
    <div class="container">
      <MovieScomp :arrayMovie="arrayMovie" />
      <TvScomp />
    </div>
  </main>
</template>

<script>
import MovieScomp from './sottocomponenti-main/MovieScomp.vue';
import TvScomp from './sottocomponenti-main/TvScomp.vue';
export default {
    name: "MainComp",
    components: { MovieScomp, TvScomp },

    props: {
      arrayMovie: Array
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