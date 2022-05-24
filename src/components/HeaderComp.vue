<template>
  <header>
    <input @keyup.enter="startToSearch" v-model.trim="titleToSearch" type="text">
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      titleToSearch: ''
    }
  },
  methods: {
    // EMIT non in-line per aggiungere la logica 'reset'
    startToSearch(){
      this.$emit('startSearch', this.titleToSearch);
      this.titleToSearch = ''
    }
  },
}
</script>

<style lang="scss" scoped>

</style>