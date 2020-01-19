<template lang="html">

  <div v-if="secondCountry" id="countryDetail">
    <h2>{{secondCountry.name}}</h2>
    <p><span>Region</span>: {{secondCountry.region.value}}</p>
    <p><span>Capital City</span>: {{secondCountry.capitalCity}}</p>
    <p><span>Income Level</span>: {{secondCountry.incomeLevel.value}}</p>
    <p><span>Longitude</span>: {{secondCountry.longitude}}</p>
    <p><span>Latitude</span>: {{secondCountry.latitude}}</p>
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
