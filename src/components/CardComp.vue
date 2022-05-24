<template>
  <div>
    <h3>{{cardData.title}}</h3>
    <h4>{{cardData.original_title}}</h4>
    <p>{{cardData.original_language}}</p>
    <p>{{cardData.vote_average}}</p>
  </div>
</template>

<script>
export default {
  name: 'CardComp',
  props: {
    cardData: Object
  }
}
</script>

<style lang="scss" scoped >

</style>