<template>
  <div id="app">
    <HeaderComp @startSearch="startSearch"/>
    <MainComp titleCards="Film" :items="movie" />
    <!-- <MainComp titleCards="Serie TV" /> -->
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
// import axios
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },

  mounted() {
    // this.getApi()
    //Qui chiamata 'i + popolari' (default)
  },

  // Data
  data() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      apiParams: {
        api_key: 'c6ddb2547d3e67a073e9212d12070041',
        language: 'it-IT',
        query: ''
      },
      movie: [],
      tv: []
    }
  },

  // Metodi
  methods: {
    startSearch(titleToSearch){
      this.apiParams.query = titleToSearch;
      if (titleToSearch.length > 0) this.getApi();
      else this.movie = []
      console.log(this.apiParams);
    },

    // chiamate axios
  getApi(){
    axios.get(this.apiUrl, {
      params: this.apiParams
    })
    .then(res => {
      console.log(res.data);
      this.movie = res.data.results
    })
    .catch(err => {
      console.log(err);
    })
  }
  },

  
}
</script>

<style lang="scss">
// importo General    Nb. in General c'è Bootstrap
@import './assets/styles/general';

</style>
