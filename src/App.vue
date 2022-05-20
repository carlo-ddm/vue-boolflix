<template>
  <div id="app">
    <HeaderComp />
    <MainComp />
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
      call:'https://api.themoviedb.org/3/search/movie?api_key=c6ddb2547d3e67a073e9212d12070041&language=it-IT&query=Harry Potter',
      callParams: {
        api_key: 'c6ddb2547d3e67a073e9212d12070041',
        language: 'it-IT',
        query: 'Harry Potter'
      }
    }
  },

// Metodi
  methods: {
    getCall(){
      axios.get(this.call, {
        params: this.callParams
      })
      .then (res => {
        console.log(res.data);
      })
    }
  },

// Mounted
  mounted() {
    this.getCall()
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
