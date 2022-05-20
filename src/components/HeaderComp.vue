<template>
  <header>

    <div
    id="logo"
    class="mx-4" >
      Logo
    </div>

    <div>

      <input type="text"
      placeholder="Cerca">

      <button
      class="mx-4">
      btn
      </button>
      
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp'
}
</script>

<style lang="scss" scoped>
// importo le mixines
@import '../assets/styles/mixines';

header {
  @include d-flex-jsb-ac;
  width: 100%;
  height: 10vh;
  border: 1px solid black;
}
</style>