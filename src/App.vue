<template>
  <div id="app">
    <HeaderComp @search="riceviInput" @type="riceviType" />
    <MainComp :arrayMovie="objsCall" :arrayTvShows="objsCallTvShows" />
  </div>
</template>

<script>
// importo axios
import axios from 'axios';

// importo componenti
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';


export default {
  name: 'App',

  // Data
  data() {
    return {
      call:'https://api.themoviedb.org/3/search/movie',
       callParams: {
        api_key: 'c6ddb2547d3e67a073e9212d12070041',
        language: 'it-IT',
        query: '',
      },
      objsCall : [],


      callTvShows: 'https://api.themoviedb.org/3/search/tv',
     
      objsCallTvShows: [],

      genereSelezionato: ''
    }
  },

  // Metodi
  methods: {
    // chiamate axios

    // Movies
    getCall(){
      axios.get(this.call, {
        params: this.callParams
      })
      .then (res => {
        this.objsCall = res.data.results;
        console.log('MOVIES --> ',this.objsCall);
      })
    },

    // Tv Shows
    getCallTvShows(){
      axios.get(this.callTvShows, {
      })
      .then(res => {
        this.objsCallTvShows = res.data.results;
        console.log('SERIE TV --> ',this.objsCallTvShows);
      })
    },

    riceviInput(text){
      this.callParams.query = text;
      this.getCall()
      this.getCallTvShows()
    },

    riceviType(genere){
      this.genereSelezionato = genere;
      console.log(this.genereSelezionato);
      if(this.genereSelezionato === 'Movie') this.getCall();
      else if (this.genereSelezionato === 'TvShows') this.getCallTvShows()
    },
  

  },

  components: {
    HeaderComp,
    MainComp
  }
}
</script>

<style lang="scss">
// importo Vars e General    Nb. in General c'è Bootstrap
@import './assets/styles/general';

</style>
