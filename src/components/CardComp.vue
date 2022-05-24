<template>
  <div class="cd_container">
    <div class="front-card">
      <img v-if="cardData.poster_path == null" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSs0NNpcOZSHRVug82lo2o07KO6UGXyu27pYA&usqp=CAU" alt="">
      <img v-else :src="`https://image.tmdb.org/t/p/w342${cardData.poster_path}`" alt="">
    </div>
    <div class="back-card d-none">
      <h3>{{cardData.title || cardData.name}}</h3>
      <h4>{{cardData.original_title || cardData.original_name}}</h4>
      <p><span :class="`fi fi-${controlloFlag(cardData.original_language)}`"></span></p>
      <span v-for="n in controlloVoto(cardData.vote_average)" :key="`stellaPiena_${cardData.id}-${n}`" ><i class="fa-solid fa-star"></i></span>
      <span v-for="n in (5 - controlloVoto(cardData.vote_average))" :key="`stellaPiena_${cardData.id}-${n}`" ><i class="fa-regular fa-star"></i></span>
    </div>
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
    },

    controlloVoto(voto){
      return Math.ceil(voto / 2)
    }
  }
}
</script>

<style lang="scss" scoped >
.cd_container {
  margin: 15px;
  overflow: hidden;
  width: 200px;
  height: 400px;
  &:hover {
    .front-card {
      display: none;
    }
    .back-card {
      display: block !important;
    }
  }
  .front-card {
    width: 100%;
    height: 100%;
    img {
      width: 100%;
    }
  }
  .back-card {
    width: 100%;
    height: 100%;
  }

}
</style>
