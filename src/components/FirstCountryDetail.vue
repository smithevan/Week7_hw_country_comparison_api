<template lang="html">

  <div v-if="firstCountry" id="countryDetail">
    <h2>{{firstCountry.name}}</h2>
    <p><span>Region</span>: {{firstCountry.region.value}}</p>
    <p><span>Capital City</span>: {{firstCountry.capitalCity}}</p>
    <p><span>Income Level</span>: {{firstCountry.incomeLevel.value}}</p>
    <p><span>Longitude</span>: {{firstCountry.longitude}}</p>
    <p><span>Latitude</span>: {{firstCountry.latitude}}</p>
  </div>

</template>

<script>
export default {
  name: 'first-country-detail',
  props: ['firstCountry']
}
</script>




<style lang="css" scoped>
</style>
