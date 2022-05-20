<template>
  <div id="app">
    <HeaderComp />
    <MainComp />
  </div>
</template>

<script>
// import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';


export default {
  name: 'App',

// Data
  data() {
    return {
      
    }
  },

// Metodi
  methods: {
    
  },

// Mounted
  mounted() {
    
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
