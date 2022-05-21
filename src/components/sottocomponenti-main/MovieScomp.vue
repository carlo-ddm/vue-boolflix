<template>
  <div>
  <CardComp v-for="(movie, index) in arrayMovie" :key="`movie_${index}`" :movie="movie"/>
  </div>
</template>

<script>
import CardComp from './CardComp.vue';
export default {
    name: "MovieScomp",
    props: {
        arrayMovie: Array
    },
    components: { CardComp }
}
</script>

<style lang="scss" scoped>

</style>