<template>
  <main>
    <div class="container">
      <MovieScomp />
      <TvScomp />
    </div>
  </main>
</template>

<script>
import MovieScomp from './sottocomponenti-main/MovieScomp.vue';
import TvScomp from './sottocomponenti-main/TvScomp.vue';
export default {
    name: "MainComp",
    components: { MovieScomp, TvScomp }
}
</script>

<style lang="scss" scoped>
// importo mixines
@import '../assets/styles/mixines';

main {
  @include d-flex-jcen-ac;
  width: 100%;
  height: 90vh; //debug

  .container {
    height: 600px; //debug
    border: 1px solid black; //debug
  }
}
</style>