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
      
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      input: ''
    }
  },

  methods: {
    sendEmit(){
      this.$emit('search', this.input);
      this.input = '';
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