<template lang="html">

  <div id="countryDetail">
    <h2 v-if="compareIncome()">
      {{firstCountry.name}} has a similar income level to {{secondCountry.name}}</h2>
    <!-- <p><span>Region</span>: {{firstCountry.region.value}}</p>
    <p><span>Capital City</span>: {{firstCountry.capitalCity}}</p>
    <p><span>Income Level</span>: {{firstCountry.incomeLevel.value}}</p>
    <p><span>Longitude</span>: {{firstCountry.longitude}}</p>
    <p><span>Latitude</span>: {{firstCountry.latitude}}</p> -->
  </div>

</template>

<script>
export default {
  name: 'country-comparison',
  props: ['firstCountry']
  ['secondCountry']
}
</script>




<style lang="css" scoped>
</style>
