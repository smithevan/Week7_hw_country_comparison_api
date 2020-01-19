<template lang="html">

  <div v-if="secondCountry" id="countryDetail">
    <h2>{{secondCountry.name}}</h2>
    <p><span>Region</span>: {{secondCountry.region.value}}</p>
  </div>

</template>

<script>
export default {
  name: 'second-country-detail',
  props: ['secondCountry']
}
</script>




<style lang="css" scoped>
</style>
