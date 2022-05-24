<template>
  <div>
    <h3>{{cardData.title || cardData.name}}</h3>
    <h4>{{cardData.original_title || cardData.original_name}}</h4>
    <p><span :class="`fi fi-${controlloFlag(cardData.original_language)}`"></span></p>
    <p>{{cardData.vote_average}}</p>
  </div>
</template>

<script>
export default {
  name: 'CardComp',
  props: {
    cardData: Object
  },

  methods: {
    controlloFlag(flag){
      if (flag === 'ja') {
        return 'jp'
      } else if (flag === 'en') {
        return 'us'
      }
    }
  }
}
</script>

<style lang="scss" scoped >

</style>