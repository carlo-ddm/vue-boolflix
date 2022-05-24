<template>
  <div class="cdd-card">
      <ul>
        <li>
          {{spettacolo.title}}
        </li>
        <li>
          {{spettacolo.original_title}}
        </li>
        <li>
          {{spettacolo.original_language}}
        </li>
        <li>
          {{spettacolo.vote_average}}
        </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CardComp',
  props: {
    spettacolo: Object,
    // tvShows: Object
  }
}
</script>

<style lang="scss" scoped>

</style>