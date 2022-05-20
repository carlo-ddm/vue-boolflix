<template>
  <main>
    <MovieScomp />
    <TvScomp />
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

</style>