<template>
  <header>

    <div
    id="logo"
    class="mx-4" >
      Logo
    </div>

    <div>

      <input type="text"
      placeholder="Cerca"
      v-model="input"
      @keyup.enter="sendEmit">

      <button
      class="mx-4"
      @click="sendEmit">
      btn
      </button>

      <select
      v-model="inputType"
      @change="sendEmitType"
      name="" id="">
      <option value="">Movies - TV Shows</option>
      <option value="Movie">Movie</option>
      <option value="TvShows">TV Shows</option>
      </select>
      
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      input: '',
      inputType: ''
    }
  },

  methods: {
    sendEmit(){
      this.$emit('search', this.input);
      this.input = '';
    },

    sendEmitType(){
      this.$emit('type', this.inputType)
    }
  },

}

</script>

<style lang="scss" scoped>
// importo mixines
@import '../assets/styles/mixines';

header {
  @include d-flex-jsb-ac;
  width: 100%;
  height: 10vh;
  border: 1px solid black;
}
</style>